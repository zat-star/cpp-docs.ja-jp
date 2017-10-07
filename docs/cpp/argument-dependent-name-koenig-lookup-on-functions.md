---
title: "関数の引数依存の名前 (Koenig) 検索 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a27b75a8be6b250e27a667a8aebf4e399fdd3f1f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>関数の引数依存名の参照 (Koenig 参照)
コンパイラは、引数依存の名前検索を使用して、非限定の関数呼び出しの定義を検索できます。 引数依存の名前検索は Koenig 検索とも呼ばれます。 関数呼び出しの各引数の型は、名前空間、クラス、構造体、共用体、またはテンプレートの階層内で定義されます。 非限定を指定すると[後置](../cpp/postfix-expressions.md)関数呼び出し、コンパイラは各引数の型に関連付けられている階層内で関数定義を検索します。  
  
## <a name="example"></a>例  
 このサンプルでは、`f()` 関数は `x` 引数を受け取ります。 `x` 引数は `A::X` 型であり、これは `A` 名前空間で定義されています。 コンパイラは `A` 名前空間を検索し、`f()` 型の引数を受け取る `A::X` 関数の定義を見つけます。  
  
```  
// argument_dependent_name_koenig_lookup_on_functions.cpp  
namespace A  
{  
   struct X  
   {  
   };  
   void f(const X&)  
   {  
   }  
}  
int main()  
{  
// The compiler finds A::f() in namespace A, which is where   
// the type of argument x is defined. The type of x is A::X.  
   A::X x;  
   f(x);     
}  
```  

