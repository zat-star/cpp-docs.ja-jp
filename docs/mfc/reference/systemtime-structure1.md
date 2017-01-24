---
title: "SYSTEMTIME 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SYSTEMTIME 構造体"
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SYSTEMTIME 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`SYSTEMTIME` 構造体は、月、日、年、曜日、時間、分、秒、およびミリ秒の各メンバーを使用して日付と時刻を表します。  
  
## 構文  
  
```  
  
      typedef struct _SYSTEMTIME {  
   WORD wYear;  
   WORD wMonth;  
   WORD wDayOfWeek;  
   WORD wDay;  
   WORD wHour;  
   WORD wMinute;  
   WORD wSecond;  
   WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### パラメーター  
 *wYear*  
 現在の年です。  
  
 *wMonth*  
 現在の月です。1 月は 1 です。  
  
 *wDayOfWeek*  
 現在の曜日です。日曜日 は 0、月曜日 は 1 などのように指定します。  
  
 *wDay*  
 月の現在の日付です。  
  
 *wHour*  
 現在の時刻 \(時間\) です。  
  
 *wMinute*  
 現在の時刻 \(分\) です。  
  
 *wSecond*  
 現在の時刻 \(秒\) です。  
  
 *wMilliseconds*  
 現在の時刻 \(ミリ秒\) です。  
  
## 使用例  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/CPP/systemtime-structure1_1.cpp)]  
  
## 必要条件  
 **ヘッダー:** winbase.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)