---
title: "コールバック項目とコールバック マスク | Microsoft Docs"
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
  - "コールバック アイテム (CListCtrl クラスの)"
  - "CListCtrl クラス, コールバック アイテムとコールバック マスク"
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# コールバック項目とコールバック マスク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

項目ごとに、リスト ビュー コントロールは、項目のアイコンのラベル テキスト、イメージ リスト内のインデックス、一連の項目の状態のビット フラグを格納します。  アプリケーションが既に項目の情報の一部を保存して、コールバック項目と個々の項目を定義できます。  
  
 "コールバック項目と **LV\_ITEM** 構造体の `pszText` と `iImage` のメンバーに適切な値を指定することにより、項目を定義します。[CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)を参照してください。  アプリケーションが項目またはサブ項目のテキストを保持する場合は、`pszText` のメンバーに **LPSTR\_TEXTCALLBACK** 値を指定します。  アプリケーションが項目のアイコンを追跡している場合は、`iImage` のメンバーに **I\_IMAGECALLBACK** 値を指定します。  
  
 コールバック項目の定義に加えて、コントロールのコールバック マスクを変更できます。  このマスクはアプリケーション、コントロールではなく、ストア データ項目の現在の状態を指定する一連のビット フラグです。  コールバック マスクはコントロールのアイテムは、特定の項目に対して適用されるコールバック項目の指定とは異なり、適用されます。  コールバック マスクは、既定では、コントロールがすべての項目の状態を追跡することを意味しています。  この既定の動作を変更するには、次の値の組み合わせにマスクを初期化してください:  
  
-   `LVIS_CUT`は、切り取りと貼り付け操作の項目としてマークされます。  
  
-   `LVIS_DROPHILITED`はドラッグ アンド ドロップ ターゲット項目として強調表示されます。  
  
-   `LVIS_FOCUSED`項目にフォーカスがあります。  
  
-   `LVIS_SELECTED`項目が選択されます。  
  
-   **LVIS\_OVERLAYMASK**アプリケーションは各項目の現在のオーバーレイ イメージのイメージ リストのインデックスが格納されます。  
  
-   **LVIS\_STATEIMAGEMASK**アプリケーションは各項目の現在の状態のイメージのイメージ リストのインデックスが格納されます。  
  
 このマスクを取得し、設定する方法の詳細については、「[CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md) と [CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md)」を参照してください。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)