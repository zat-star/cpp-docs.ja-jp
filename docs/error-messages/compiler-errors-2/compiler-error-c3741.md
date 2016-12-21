---
title: "コンパイラ エラー C3741 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3741"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3741"
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3741
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : event\_receiver の 'layout\_dependent' パラメーターが True の場合、コクラスでなければなりません。  
  
 [event\_receiver](../../windows/event-receiver.md) クラスが `layout_dependent=true`の場合、そのクラスには [coclass](../../windows/coclass.md) 属性も必要です。  
  
 次の例では C3741 エラーが生成されます。  
  
```  
// C3741.cpp  
// compile with: /c  
// C3741 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I{ HRESULT f(); };  
  
// Delete the following line to resolve.  
[ event_receiver(com, layout_dependent=true)]  
  
// class or struct must be declared with coclass  
// Uncomment the following line to resolve.  
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct R : I {  
   HRESULT f(){ return 0; }  
   R(){}  
   R(I* a){ __hook(I, a); }  
};  
```