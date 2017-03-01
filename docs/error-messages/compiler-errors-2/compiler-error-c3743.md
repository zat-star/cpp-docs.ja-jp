---
title: "コンパイラ エラー C3743 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: 8
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
ms.openlocfilehash: 1a7f7e7b561e20f962aef4757d1248f1b7d3c6f5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3743"></a>コンパイラ エラー C3743
event_receiver の 'layout_dependent' パラメーターが True の場合にのみ、すべてのインターフェイスをフック/アンフックできます。  
  
 [_ _Unhook](../../cpp/unhook.md)関数に渡される値に基づくかかるパラメーターの数が変化、`layout_dependent`内のパラメーター、 [event_receiver](../../windows/event-receiver.md)クラスです。  
  
 次の例では、c3743 エラーが生成されます。  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```
