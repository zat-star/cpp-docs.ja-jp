---
title: "MSG Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSG 構造体"
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MSG 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`MSG` 構造体はスレッドのメッセージ キューからメッセージ情報が含まれます。  
  
## 構文  
  
```  
  
      typedef struct tagMSG {     // msg    
   HWND hwnd;  
   UINT message;  
   WPARAM wParam;  
   LPARAM lParam;  
   DWORD time;  
   POINT pt;  
} MSG;  
```  
  
#### パラメーター  
 *hwnd*  
 ウィンドウ プロシージャでメッセージを受け取るウィンドウを指定します。  
  
 `message`  
 メッセージの番号を指定します。  
  
 `wParam`  
 メッセージについての追加情報を指定します。  厳密な意味は **メッセージ** のメンバーの値によって異なります。  
  
 `lParam`  
 メッセージについての追加情報を指定します。  厳密な意味は **メッセージ** のメンバーの値によって異なります。  
  
 `time`  
 メッセージがポストされた時間を指定します。  
  
 `pt`  
 メッセージがポストされたときに、カーソル位置を画面座標で指定します。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)