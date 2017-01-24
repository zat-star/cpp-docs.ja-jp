---
title: "スピン ボタンのスタイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl クラス, スタイル"
  - "スピン ボタン コントロール, スタイル"
  - "スタイル, CSpinButtonCtrl"
  - "スタイル, スピン ボタン コントロール"
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スピン ボタンのスタイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スピン ボタン \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\) の設定の多くは、スタイルによって制御されます。  ダイアログ エディターの **\[プロパティ\]** ウィンドウを使用すると、次のスタイルを設定できます。  
  
-   縦または横**向き**。  矢印ボタンの方向を制御します。  `UDS_HORZ` のスタイルに関連付けられます。  
  
-   アタッチされていません、左の**配置** 1、またはアクセス許可。  スピン ボタンの場所を制御します。  左の位置関連ウィンドウの横にあるスピン ボタン。  関連するウィンドウの幅は、スピン ボタンを入力できるようになります。  `UDS_ALIGNLEFT` と `UDS_ALIGNRIGHT` のスタイルに関連付けられます。  
  
-   **Auto Buddy**は、スピン ボタンに関連ウィンドウとして自動的に Z オーダーの前のウィンドウを選択します。  ダイアログ テンプレートでは、this はタブ オーダーのスピン ボタンに先行するコントロールです。  `UDS_AUTOBUDDY` のスタイルに関連付けられます。  
  
-   現在位置を変更するときに**Set Buddy Integer**スピン コントロールは関連ウィンドウのキャプションをインクリメントし、デクリメントします。  `UDS_SETBUDDYINT` のスタイルに関連付けられます。  
  
-   **No Thousands**は関連ウィンドウのキャプションの値で桁区切り記号は挿入されません。  `UDS_NOTHOUSANDS` のスタイルに関連付けられます。  
  
    > [!NOTE]
    >  関連コントロールから整数値を取得するには、ダイアログ データ エクスチェンジ \(DDX\) を使用する場合は、このスタイルを設定します。  `DDX_Text` は 埋め込まれたな区切り記号数値は使用できません。  
  
-   値がコントロールの範囲を超えてインクリメントされるか、デクリメントされるように**右端で折り返す**により「ラップ」位置になります。  `UDS_WRAP` のスタイルに関連付けられます。  
  
-   ↑キーおよび↓キーを押すと**方向キー**スピン ボタンの位置をインクリメントするか、デクリメントします。  `UDS_ARROWKEYS` のスタイルに関連付けられます。  
  
## 参照  
 [CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)   
 [コントロール](../mfc/controls-mfc.md)