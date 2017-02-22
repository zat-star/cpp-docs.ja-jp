---
title: "ツール バー コントロールでのイメージ リストの使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl クラス, イメージ リスト"
  - "イメージ リスト [C++], ツール バー コントロール"
  - "ツール バー コントロール [MFC], イメージ"
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ツール バー コントロールでのイメージ リストの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定では一つのビットマップとして、ToolBar コントロール内のボタンによって使用されるイメージ格納されます。  ただし、一連のイメージ リストにあるボタン イメージを格納できます。  ツール バー コントロール オブジェクトは 3 つまでのイメージ リストを使用する:  
  
-   有効なイメージ リストは現在有効になっているツール バー ボタンのイメージが含まれます。  
  
-   無効イメージのリストには、現在無効になるツール バー ボタンのイメージが含まれます。  
  
-   強調表示されたイメージ リストは現在強調表示されているツール バー ボタンのイメージが含まれています。  このイメージ リストはツール バーが **TBSTYLE\_FLAT** のスタイルを使用する場合にのみ使用されます。  
  
 これらのイメージ リストは、ツール バー コントロールによって `CToolBarCtrl` オブジェクトに関連付ける場合に使用されます。  この関連付けは、[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)[SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)と [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)を呼び出すことによって実現されます。  
  
 既定で、MFC アプリケーション ツール バーを実装するために `CToolBar` クラスを使用します。  ただし `CToolBarCtrl` の埋め込まれたなオブジェクトを取得するために、`GetToolBarCtrl` のメンバー関数を使用できます。  返されたオブジェクトを使用して `CToolBarCtrl` のメンバー関数を呼び出すことができます。  
  
 次の例では `CToolBarCtrl` オブジェクト \(`m_ToolBarCtrl`\) \(`m_ToolBarDisabledImages`\) の有効な \(`m_ToolBarImages`\) 無効イメージ リストを割り当てると、この手法を示します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/CPP/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  ツール バー オブジェクトで使用されるイメージ リストは、永続的なオブジェクトである必要があります。  したがって、一般に MFC クラスのデータ メンバーで; この例では、メイン フレーム ウィンドウのクラスです。  
  
 イメージ リストが `CToolBarCtrl` オブジェクトに関連付けられている場合、フレームワークは自動的に適切なボタン イメージを表示します。  
  
## 参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)