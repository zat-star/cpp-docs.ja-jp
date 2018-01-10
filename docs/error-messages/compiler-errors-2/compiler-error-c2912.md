---
title: "コンパイラ エラー C2912 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2912
dev_langs: C++
helpviewer_keywords: C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 88533f00ebf926823d6493aa1027013638694a43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2912"></a>コンパイラ エラー C2912
明示的な特殊化 'declaration' は関数テンプレートの特殊化ではありません  
  
 template 宣言がない関数は特殊化できません。  
  
 次の例では C2912 が生成されます。  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。すべての明示的な特殊化で、そのパラメーターとしてプライマリ テンプレートのパラメーターと一致するパラメーターを選択する必要があります。  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```