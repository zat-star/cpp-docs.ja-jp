---
title: "ツール バー コントロールの外観のカスタマイズ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBSTYLE_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBar クラス, スタイル"
  - "CToolBarCtrl クラス, オブジェクト スタイル"
  - "フラット ツール バー"
  - "TBSTYLE_ スタイル"
  - "ツール バー コントロール [MFC], スタイル"
  - "透過ツール バー"
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ツール バー コントロールの外観のカスタマイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CToolBarCtrl` クラスは、ツール バー オブジェクトの外観 \(および場合によっては、動作\) によって影響を受ける多数のスタイルを提供します。  `CToolBarCtrl::Create` \(または `CToolBar::CreateEx`\) メンバー関数の `dwCtrlStyle` パラメーターの設定によって、ツール バー オブジェクトを変更します。最初にツール バー コントロールを作成する場合。  
  
 次のスタイルは、ツール バー ボタンの「3D」、およびボタン テキストの配置に影響する:  
  
-   **TBSTYLE\_FLAT**はツール バーとボタンの両方が透明なフラット ツール バーを作成します。  ボタン テキストをボタンのビットマップの下に表示されます。  このスタイルを使用する場合、カーソルの下に、自動的に強調表示されます。  
  
-   **TBSTYLE\_TRANSPARENT**は透明なツール バーを作成します。  透明なツール バーで、ツール バーは透過的ですが、ボタンは無効です。  ボタン テキストをボタンのビットマップの下に表示されます。  
  
-   ボタンのビットマップの右側の**TBSTYLE\_LIST**の場所のボタン テキスト。  
  
> [!NOTE]
>  無効にするには、**TBSTYLE\_FLAT** 問題を再描画すればツール バー オブジェクトが表示される前に **TBSTYLE\_TRANSPARENT** のスタイルを設定する必要があります。  
  
 次のスタイルでは、ユーザーがツール バーをドラッグ アンド ドロップを使用してツール バー オブジェクト内の個々のボタンの位置を変更できるかどうかの確認:  
  
-   **TBSTYLE\_ALTDRAG**は Alt キーを押しながら、ユーザーがドラッグすることによって、ツール バー ボタンの位置を変更することができます。  このスタイルが指定されていない場合、ユーザーはボタンをドラッグしながら Shift キーを保持する必要があります。  
  
    > [!NOTE]
    >  `CCS_ADJUSTABLE` のスタイルは、ツール バー ボタンがドラッグできるようにするように指定する必要があります。  
  
-   **TBSTYLE\_REGISTERDROP**は、マウス ポインターがツール バー ボタンを渡すときドロップ ターゲット オブジェクトを要求するに **TBN\_GETOBJECT** 通知メッセージを生成します。  
  
 残りのスタイルは、ツール バー オブジェクトをとおしてビジュアル要素に影響する:  
  
-   `TBSTYLE_WRAPABLE`はボタンの複数行を追加できるツール バーを作成します。  ツール バー ボタンは次の行にツール バーが同じ行に含まれるすべてのボタンには"縮小変換に「ラップ」を表示できます。  ラップすると、分離と nongroup の境界に一致します。  
  
-   **TBSTYLE\_CUSTOMERASE**は  `WM_ERASEBKGND` メッセージを処理するときに **NM\_CUSTOMDRAW** 通知メッセージを生成します。  
  
-   `TBSTYLE_TOOLTIPS`はツール バーのボタンの説明テキストを表示するには、アプリケーションが使用できるツール ヒント コントロールを作成します。  
  
 ツール バー スタイルと拡張スタイルの一覧については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [Toolbar Control and Button のスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439) と [ツールバーの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb760430) を参照してください。  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)