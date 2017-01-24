---
title: "ヘッダー コントロールおよびリスト コントロール | Microsoft Docs"
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
  - "CHeaderCtrl クラス, CListCtrl を使用する"
  - "CListCtrl クラス, ヘッダー コントロール"
  - "CListCtrl クラス, CHeaderCtrl を使用する"
  - "コントロール [MFC], ヘッダー"
  - "ヘッダー コントロール"
  - "ヘッダー コントロール, リスト コントロール (ヘッダー コントロールで使用する)"
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロールおよびリスト コントロール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどの場合、[CListCtrl](../Topic/CListCtrl%20Class.md) または [CListView](../mfc/reference/clistview-class.md) オブジェクトに埋め込まれているヘッダー コントロールを使用します。  ただし、別のヘッダー コントロール オブジェクトが、列または行に配置されたデータの操作などの適切な [CView](../Topic/CView%20Class.md)\-派生オブジェクトの場合もあります。  このような場合、埋め込まれたなヘッダー コントロールの既定の外観と動作をより大きいコントロールが必要です。  
  
 一般的なケースでは、ヘッダー コントロールに標準を提供する既定の動作、[CListCtrl](../Topic/CListCtrl%20Class.md) または [CListView](../mfc/reference/clistview-class.md) を代わりに使用することもできます。  既定のヘッダー コントロール機能が必要な場合は、リスト ビュー コモン コントロールに埋め込まれた `CListCtrl` を使用します。  既定のヘッダー コントロール機能が必要な場合は、ビュー オブジェクトに埋め込まれた [CListView](../mfc/reference/clistview-class.md) を使用します。  
  
> [!NOTE]
>  これらのコントロールは、リスト ビュー コントロールが `LVS_REPORT` のスタイルを使用して作成されている場合にのみ、組み込みのヘッダー コントロールが含まれます。  
  
 ほとんどの場合、埋め込まれたなヘッダー コントロールの外観が格納されたリスト ビュー コントロールのスタイルを変更することによって変更できます。  また、ヘッダー コントロールに関する情報は親リスト ビュー コントロールのメンバー関数で取得できます。  ただし、完全に制御およびアクセスには、埋め込まれたなヘッダー コントロールの属性とスタイルに、ヘッダー コントロール オブジェクトへのポインターを取得することをお勧めします。  
  
 埋め込まれたなヘッダー コントロール オブジェクトは呼び出しで **CListCtrl** または `CListView` から各クラスの `GetHeaderCtrl` メンバー関数にアクセスできます。  次のコードで例を示します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/CPP/header-control-and-list-control_1.cpp)]  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ヘッダー コントロールでイメージ リストを使用します。](../mfc/using-image-lists-with-header-controls.md)  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)