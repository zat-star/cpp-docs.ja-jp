---
title: "MINMAXINFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MINMAXINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MINMAXINFO 構造体"
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MINMAXINFO 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`MINMAXINFO` 構造体はウィンドウの子ウィンドウのサイズと位置の情報を最小値と最大トラッキング サイズが含まれます。  
  
## 構文  
  
```  
  
      typedef struct tagMINMAXINFO {  
   POINT ptReserved;  
   POINT ptMaxSize;  
   POINT ptMaxPosition;  
   POINT ptMinTrackSize;  
   POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### パラメーター  
 *ptReserved*  
 内部使用のために予約されています。  
  
 *ptMaxSize*  
 最大化された幅 \(point.x\) とウィンドウの子ウィンドウの高さ \(point.y\) を指定します。  
  
 `ptMaxPosition`  
 最大化されたウィンドウ \(point.x\) の左端の位置と最大化されたウィンドウ \(point.y\) の上端の位置を指定します。  
  
 *ptMinTrackSize*  
 最小幅の追跡 \(point.x\) とトラッキング ウィンドウの高さの最小 \(point.y\) を指定します。  
  
 *ptMaxTrackSize*  
 最大追跡幅 \(point.x\) とトラッキング ウィンドウの高さの最大 point.y \(\) を指定します。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)