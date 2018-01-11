---
title: "コンパイラの警告 (レベル 1) C4683 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4683
dev_langs: C++
helpviewer_keywords: C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a8ca498a3c95a1b37229f6ac973cf74a8e28ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4683"></a>コンパイラの警告 (レベル 1) C4683
**'**   
 ***関数*': イベント ソースが 'out' のパラメーター以外の複数のイベント ハンドラーをフックするときに注意**  
  
 1 つ以上のイベント シンクが COM イベント ソースをリッスンしている場合は、out パラメーターの値が無視可能性があります。  
  
 次のような状況で、メモリ リークが発生する注意してください。  
  
1.  メソッドに内部的に割り当てられると、たとえば BSTR を out パラメーターがあるかどうか * です。  
  
2.  イベントに複数のハンドラーがある場合 (はマルチキャスト イベント)  
  
 メモリ リークの原因は、out パラメーターが複数のハンドラーで設定が最後のハンドラーによってのみ、呼び出しサイトに返されることです。  
  
 次の例では、C4683 が生成されます。  
  
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