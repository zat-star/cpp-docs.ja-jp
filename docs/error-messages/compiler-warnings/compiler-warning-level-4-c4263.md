---
title: "コンパイラの警告 (レベル 4) C4263 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4263
dev_langs: C++
helpviewer_keywords: C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47f871f956ef07eebc2f528182dde58ba0fa3b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4263"></a>コンパイラの警告 (レベル 4) C4263
'function': メンバー関数はどの基底クラス仮想メンバー関数をオーバーライドしません  
  
 クラスの関数定義では、同じ数または引数の型ではありませんが、基底クラスの仮想関数と同じ名前を持ちます。 基本クラスの仮想関数と、効果的に非表示にします。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では、C4263 が生成されます。  
  
```  
// C4263.cpp  
// compile with: /W4  
#pragma warning(default:4263)  
#pragma warning(default:4264)  
class B {  
public:  
   virtual void func();  
};  
  
class D : public B {  
   void func(int);   // C4263  
};  
  
int main() {  
}  
```