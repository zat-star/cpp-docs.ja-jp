---
title: "コンパイラ エラー C3733 | Microsoft Docs"
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
  - "C3733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3733"
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event' : COM イベントを指定する構文が正しくありません。'\_\_interface' が指定されていない可能性があります。  
  
 COM イベントに間違った構文が使用されています。  このエラーを解決するには、イベントの型を変更するか、または COM イベントの規則に準拠するように構文を書き直します。  
  
 次の例では警告 C3733 が生成されます。  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```