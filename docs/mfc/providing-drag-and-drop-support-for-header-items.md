---
title: "ヘッダー項目に対するドラッグ アンド ドロップのサポート | Microsoft Docs"
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
  - "CHeaderCtrl クラス, ドラッグ アンド ドロップのサポート"
  - "HDN_ 通知"
  - "HDS_DRAGDROP 形式"
  - "ヘッダー項目 (ヘッダー コントロールの)"
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー項目に対するドラッグ アンド ドロップのサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヘッダー項目にドラッグ アンド ドロップのサポートを提供するには、`HDS_DRAGDROP` のスタイルを指定します。  項目ヘッダーのドラッグ アンド ドロップのサポートは、ヘッダー コントロールのヘッダー項目の順序を変更できます。  既定の動作では、ヘッダー項目がある場合、ドラッグ ヘッダー項目の半透明なドラッグ イメージと新しい位置の視覚的なインジケーターを提供します。  
  
 共通のドラッグ アンド ドロップ機能と同様に、**HDN\_BEGINDRAG** と **HDN\_ENDDRAG** 通知を処理して既定のドラッグ アンド ドロップの動作を拡張できます。  また [CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md) メンバー関数をオーバーライドすることによって、イメージの外観をカスタマイズできます。  
  
> [!NOTE]
>  リスト コントロールの埋め込まれたなヘッダー コントロールにドラッグ アンド ドロップのサポートを提供する場合は、[変更のリスト コントロールのスタイル](../Topic/Changing%20List%20Control%20Styles.md) の拡張スタイル"を参照してください。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)