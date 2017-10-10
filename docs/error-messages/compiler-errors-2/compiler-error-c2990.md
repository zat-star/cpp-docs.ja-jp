---
title: "コンパイラ エラー C2990 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9a2433bec7992c73fb7e9b7f358e89b7e75da384
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2990"></a>コンパイラ エラー C2990
'class': 非クラス型既にクラス型として宣言されています。  
  
 非ジェネリックまたはテンプレート クラスは、ジェネリックまたはテンプレート クラスを再定義します。 競合のヘッダー ファイルを確認してください。  
  
 次の例では、C2990 が生成されます。  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 C2990 も発生する可能性が重大な変更について、Visual C コンパイラで Visual C 2005 です。コンパイラは、今すぐ、同じ種類の複数の宣言がテンプレートの仕様と一致させることが必要です。  
  
 次の例では、C2990 が生成されます。  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```
