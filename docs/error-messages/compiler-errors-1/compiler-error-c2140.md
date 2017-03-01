---
title: "コンパイラ エラー C2140 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2140
dev_langs:
- C++
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 94cb118244e1d93c1a084aca898c2f417fd88442
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2140"></a>コンパイラ エラー C2140
'type': ジェネリック型パラメーターに依存する型がコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません  
  
 無効な型の指定子は、型の特徴が渡されました。  
  
 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では、c2140 エラーを生成します。  
  
```  
// C2140.cpp  
// compile with: /clr /c  
template <class T>  
  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class x {};  
  
generic <class T>  
ref class C {  
   void f() {  
      System::Console::WriteLine(__is_polymorphic(T));   // C2140  
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140  
  
      System::Console::WriteLine(__is_polymorphic(x));   // OK  
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK  
   }  
};  
```
