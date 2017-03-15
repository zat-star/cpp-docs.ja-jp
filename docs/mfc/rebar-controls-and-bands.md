---
title: "Rebar コントロールとバンド | Microsoft Docs"
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
  - "バンド, rebar コントロールで"
  - "rebar コントロール, 処理 (バンドの)"
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Rebar コントロールとバンド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

rebar のコントロールの主な目的でその子ウィンドウ、コモン ダイアログ コントロール、メニュー、ツール バーのコンテナーとして機能します。  このコンテインメントは「バンドの概念がサポートされます」。各 rebar バンド、グリップ バー、ビットマップ、テキスト ラベル、子ウィンドウを組み合わせて含めることができます。  
  
 クラス `CReBarCtrl` に、取得し、処理するために使用した rebar バンドの情報できる多くのメンバー関数が使用されています:  
  
-   [GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)は rebar のコントロールの現在のバンドの数を取得します。  
  
-   [GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)は指定バンドの情報を **REBARBANDINFO** 構造体を初期化します。  [SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md) の対応するメンバー関数があります。  
  
-   [GetRect](../Topic/CReBarCtrl::GetRect.md)は指定バンドの外接する四角形を取得します。  
  
-   [GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)は rebar コントロールのバンドの行数を取得します。  
  
-   [IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)は指定バンドのインデックスを取得します。  
  
-   [GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)はバンドの境界を取得します。  
  
 操作に加えて、複数のメンバー関数は、特定の rebar バンドを操作できます。  
  
 [InsertBand](../Topic/CReBarCtrl::InsertBand.md) と [DeleteBand](../Topic/CReBarCtrl::DeleteBand.md) は rebar バンドを追加および削除します。  [MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md) と [MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md) は特定の rebar バンドの現在のサイズに影響します。  [MoveBand](../Topic/CReBarCtrl::MoveBand.md) は 特定の rebar バンドのインデックスを変更します。  [ShowBand](../Topic/CReBarCtrl::ShowBand.md) の 表示と非表示の rebar バンド。  
  
 次の例は、既存の Rebar のコントロール \(`m_wndReBar`\) にあるツール バー`m_wndToolBar`バンド \(\) を追加する方法を示します。  バンドは `rbi` 構造体を初期化し、`InsertBand` のメンバー関数を呼び出すことによって記述されています:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/CPP/rebar-controls-and-bands_1.cpp)]  
  
## 参照  
 [CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)