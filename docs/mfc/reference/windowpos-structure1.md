---
title: "WINDOWPOS 構造体 | Microsoft Docs"
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
  - "WINDOWPOS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPOS 構造体"
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WINDOWPOS 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`WINDOWPOS` 構造体は、ウィンドウのサイズと位置に関する情報が含まれます。  
  
## 構文  
  
```  
  
      typedef struct tagWINDOWPOS { /* wp */  
   HWND hwnd;  
   HWND hwndInsertAfter;  
   int x;  
   int y;  
   int cx;  
   int cy;  
   UINT flags;  
} WINDOWPOS;  
```  
  
#### パラメーター  
 *hwnd*  
 ウィンドウを識別します。  
  
 *hwndInsertAfter*  
 このウィンドウに配置されるウィンドウを識別します。  
  
 *x*  
 ウィンドウの左端の位置を指定します。  
  
 *y*  
 ウィンドウの右端の位置を指定します。  
  
 `cx`  
 ピクセルにウィンドウの幅を指定します。  
  
 `cy`  
 ピクセルにウィンドウの高さを指定します。  
  
 `flags`  
 オプション ウィンドウを配置することを指定します。  このメンバーは、次の値が 1 である可能性があります:  
  
-   **SWP\_DRAWFRAME**はウィンドウの周囲にフレームを \(ウィンドウの説明クラスで定義されている\) を描画します。  ウィンドウが `WM_NCCALCSIZE` メッセージを受け取ります。  
  
-   **SWP\_FRAMECHANGED** ウィンドウのサイズが変化されていない場合でも、ウィンドウに `WM_NCCALCSIZE` メッセージを送信します。  このフラグが指定されていない場合、`WM_NCCALCSIZE` メッセージはウィンドウのサイズが実際に変化しているときにだけ送られます。  
  
-   **SWP\_HIDEWINDOW** ウィンドウを非表示にします。  
  
-   `SWP_NOACTIVATE` ウィンドウをアクティブにしません。  
  
-   **SWP\_NOCOPYBITS** クライアント領域の内容全体を破棄します。  このフラグが指定されていない場合、クライアント領域の有効な内容はすべて保存されます。保存された内容は、ウィンドウのサイズや位置が再び変更されたときにクライアント領域に復元されます。  
  
-   `SWP_NOMOVE`は現在位置を保持します \(**x** と **y** のメンバーを無視します\)。  
  
-   **SWP\_NOOWNERZORDER** オーナー ウィンドウの Z オーダーの位置を変更しません。  
  
-   `SWP_NOSIZE`は現在のサイズを保持します \(**cx** と **cy** のメンバーを無視します\)。  
  
-   **SWP\_NOREDRAW** 変更があっても再描画しません。  
  
-   **SWP\_NOREPOSITION SWP\_NOOWNERZORDER** と同じです。  
  
-   **SWP\_NOSENDCHANGING** ウィンドウが `WM_WINDOWPOSCHANGING` メッセージを受信しないようにします。  
  
-   `SWP_NOZORDER`は現在の順序を保持します \(**hwndInsertAfter** のメンバーを無視します\)。  
  
-   **SWP\_SHOWWINDOW** ウィンドウを表示します。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)