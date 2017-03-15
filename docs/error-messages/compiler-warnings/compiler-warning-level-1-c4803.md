---
title: "コンパイラの警告 (レベル 1) C4803 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
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
ms.openlocfilehash: 2581d4240306e88d75fe5fcc0249371005853b7e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4803"></a>コンパイラの警告 (レベル 1) C4803
'method': raise メソッド、イベントと異なるストレージ クラスには 'event'  
  
イベント メソッドには、イベントの宣言と同じストレージ クラスが必要です。 コンパイラは、ストレージ クラスが同じになるように、イベントのメソッドを調整します。  
  
この警告をインターフェイスからイベントを実装するクラスがある場合に発生することができます。 ありません、コンパイラでは、インターフェイス内でイベントの発生メソッドの生成が暗黙的に実行します。 クラスでそのインターフェイスを実装するときに、コンパイラは raise メソッドを生成して暗黙的にしてそのメソッドは仮想、そのため、警告します。 イベントの詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
参照してください[警告](../../preprocessor/warning.md)プラグマについては、警告を無効にする方法です。  
  
## <a name="example"></a>例  
 次の例では、C4803 を生成します。  
  
```  
// C4803.cpp  
// compile with: /clr /W1  
using namespace System;  
  
public delegate void Del();  
  
ref struct E {  
   Del ^ _pd1;  
   event Del ^ E1 {  
      void add (Del ^ pd1) {  
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));  
      }  
  
      void remove(Del^ pd1) {  
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));  
      }  
  
      virtual void raise() {   // C4803 warning (remove virtual)  
         if (_pd1)  
            _pd1();  
      }  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E ^ ep = gcnew E;  
   ep->E1 += gcnew Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= gcnew Del(ep, &E::func);  
   ep->E1();  
}  
```  

