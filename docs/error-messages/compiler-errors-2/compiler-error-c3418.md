---
title: "コンパイラ エラー C3418 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3418
dev_langs: C++
helpviewer_keywords: C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e36fa3a27a122db715f84405b0484508fb13e8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3418"></a>コンパイラ エラー C3418
アクセス指定子 'specifier' はサポートされていません  
  
CLR アクセス指定子が正しく指定されていません。  詳細については、型の可視性とメンバーの可視性で参照してください[する方法: を定義して消費クラスと構造体 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では C3418 が生成されます。  
  
```cpp  
// C3418.cpp  
// compile with: /clr /c  
ref struct m {  
internal public:   // C3418  
   void test(){}  
};  
  
ref struct n {  
internal:   // OK  
   void test(){}  
};  
```