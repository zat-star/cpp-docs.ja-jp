---
title: "コンパイラの警告 (レベル 3) C4823 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4823
dev_langs: C++
helpviewer_keywords: C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18e041bd9a013779a37dc2460b8e1913b69d734b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4823"></a>コンパイラの警告 (レベル 3) C4823
'function': を使用して固定ポインターが、アンワインド セマンティクスが有効ではありません。 /EHa を使用してください。  
  
固定を解除するには、ブロック スコープで宣言された固定ポインターが指すマネージ ヒープ上のオブジェクトには、コンパイラは、「なりすましている」固定ポインターにポインターを null にするデストラクターを持つ、ローカルのクラスのデストラクターの動作をシミュレートします。 例外をスローした後、デストラクターへの呼び出しを有効にする必要がありますを有効にするオブジェクト アンワインディングを使用して行うことができますが[/EHsc](../../build/reference/eh-exception-handling-model.md)です。  
  
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
