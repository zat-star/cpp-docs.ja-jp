---
title: "CStatusBarCtrl の設定値 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス, 設定"
  - "ステータス バー コントロール, 設定"
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CStatusBarCtrl の設定値
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) のステータス ウィンドウの既定の場所は、親ウィンドウの下部に合わせて、アイテムが親ウィンドウのクライアント領域の上部に表示されるように `CCS_TOP` のスタイルを指定できます。  
  
 `CStatusBarCtrl` のステータス ウィンドウの右端にサイズ変更グリップを含めるように **SBARS\_SIZEGRIP** のスタイルを指定できます。  サイズ変更グリップはサイズ変更境界に似ています; 親ウィンドウのサイズを変更するときにドラッグし、ユーザーがクリックできるのは四角形領域です。  
  
> [!NOTE]
>  `CCS_TOP` と **SBARS\_SIZEGRIP** のスタイルを組み合わせると、結果サイズ変更グリップ、システムがステータス ウィンドウで描画が機能しません。  
  
 ステータス ウィンドウのウィンドウ プロシージャは自動的にコントロール ウィンドウの初期のサイズと位置を設定します。  幅は、親ウィンドウのクライアント領域の型と同じになります。  高さはステータス ウィンドウのデバイス コンテキストにとウィンドウのリテイナーの幅で現在選択されているフォントの測度に基づいています。  
  
 ウィンドウ プロシージャは自動的に `WM_SIZE` メッセージが受信されるたびにステータス ウィンドウのサイズを調整します。  通常、親ウィンドウのサイズを変更すると、ステータス `WM_SIZE` は親ウィンドウにメッセージを送信します。  
  
 [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)を呼び出して、最小限の高さをピクセル単位で指定するステータス ウィンドウの描画領域の最小の高さを設定できます。  描画領域は、Windows のリテイナーは含まれません。  
  
 [GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)を呼び出してステータス ウィンドウの境界の幅を取得します。  このメンバー関数は、四角形の水平の境界、垂直の境界と境界の幅を受け取る 3 要素のな配列へのポインターが含まれています。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)