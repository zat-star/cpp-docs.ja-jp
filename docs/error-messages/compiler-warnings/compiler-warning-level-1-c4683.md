---
title: "コンパイラの警告 (レベル 1) C4683 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4683"
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラの警告 (レベル 1) C4683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***function* ': イベントソースに 'out' パラメーターが存在します。複数のイベント ハンドラーをフックするときに注意が必要です。**  
  
 複数のイベント シンクが COM イベント ソースを待機している場合は、out パラメーターの値が無視されることがあります。  
  
 以下の場合にはメモリ リークが発生します。  
  
1.  BSTR \* など、内部的に割り当てられた out パラメーターがメソッドにある場合。  
  
2.  イベントに複数のハンドラーがある場合 \(マルチキャスト イベント\)。  
  
 メモリ リークの原因は、out パラメーターが複数のハンドラーによって設定されているのに、最後のハンドラーによってのみ呼び出しサイトに返されているためです。  
  
 次の例では警告 C4683 が生成されます。  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```