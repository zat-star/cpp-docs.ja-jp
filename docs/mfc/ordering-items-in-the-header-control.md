---
title: "ヘッダー コントロールの項目の並べ替え | Microsoft Docs"
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
  - "DS_DRAGDROP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DS_DRAGDROP 通知"
  - "GetOrderArray メソッド"
  - "ヘッダー コントロール, 順序付け (項目の)"
  - "OrderToIndex メソッド"
  - "手順"
  - "手順, ヘッダー コントロール項目"
  - "SetOrderArray メソッド"
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロールの項目の並べ替え
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ヘッダー コントロールへの追加された項目](../mfc/adding-items-to-the-header-control.md)がある場合は、次の関数の順序に関する情報を処理するか、または取得できます。:  
  
-   [CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md) と [CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)  
  
     項目ヘッダーの左から右の順序を取得し、設定します。  
  
-   [CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md)。  
  
     特定のヘッダー項目のインデックス値を取得します。  
  
 前のメンバー関数に加えて、`HDS_DRAGDROP` のスタイルはユーザーがヘッダー コントロール内のヘッダー項目をドラッグ アンド ドロップすることができます。  詳細については、「[ヘッダー項目にドラッグ アンド ドロップのサポートを提供します。](../mfc/providing-drag-and-drop-support-for-header-items.md)」を参照してください。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)