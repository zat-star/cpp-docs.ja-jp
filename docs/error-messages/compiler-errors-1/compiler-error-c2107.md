---
title: "コンパイラ エラーと、c2107 エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2107
dev_langs:
- C++
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: dd2386049448af6bbf031b8568294ffae47cd7b5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2107"></a>コンパイラ エラー C2107
無効なインデックスです、間接参照は許可されていません  
  
 ポインターではない式に添字が使われています。  
  
## <a name="example"></a>例  
 値型の `this` ポインターを不正に使用して型の既定のインデクサーにアクセスすると、C2107 エラーが発生します。 詳細については、次を参照してください。[このセマンティクス ポインター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)します。  
  
 次の例では、c2107 エラーが生成されます。  
  
```  
// C2107.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property String ^ default[String ^] {  
      String ^ get(String ^ data) {  
         return "abc";  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this["aa"]);   // C2107  
      Console::WriteLine("{0}", this->default["aa"]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```
