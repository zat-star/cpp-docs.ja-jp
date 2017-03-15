---
title: "コンパイラの警告 (レベル 3) C4823 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ea03723f9ccae2348a47ae4894097f5cd9f8b5a1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4823"></a>コンパイラの警告 (レベル 3) C4823
'function': を使用して固定ポインターは、アンワインド セマンティクスが有効になっていません。 /EHa の使用を検討してください。  
  
固定を解除するには、ブロック スコープで宣言された固定ポインターが指すマネージ ヒープ上のオブジェクトには、コンパイラは、「装った」は、固定ポインターにポインターを null にするデストラクターを持つローカルのクラスのデストラクターの動作をシミュレートします。 例外をスローした後、デストラクターへの呼び出しを有効にする必要がありますを有効にしたオブジェクトのアンワインドにこれを使用して行うことができます[/EHsc](../../build/reference/eh-exception-handling-model.md)します。  
  
手動でオブジェクトの固定を解除し、警告を無視できます。  
  
## <a name="example"></a>例  
次の例では、C4823 を生成します。  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  

