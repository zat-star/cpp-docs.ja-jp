---
title: "ツリー コントロールのイメージ リスト | Microsoft Docs"
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
  - "CTreeCtrl クラス, イメージ リスト"
  - "イメージ [C++], 一覧 (ツリー コントロール内の)"
  - "ツリー コントロール, イメージ リスト"
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ツリー コントロールのイメージ リスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) の各項目には、関連付けられたビットマップ イメージのペアを持つことができます。  イメージが項目のラベルの左側に表示されます。  1 種類のイメージは項目が選択されていない場合、項目が選択され、もう一方が表示されるときに表示されます。  たとえば、項目が選択されていない場合、閉じるフォルダーを選択すると、開くフォルダーを表示することもできます。  
  
 項目のイメージを使用するには、[CImageList](../Topic/CImageList%20Class.md) オブジェクトを構築し、関連付けられたイメージ リストを作成するために [CImageList::Create](../Topic/CImageList::Create.md) 関数を使用して、イメージ リストを作成する必要があります。  その後、目的のビットマップをリストに追加して、ツリー コントロールで [SetImageList](../Topic/CTreeCtrl::SetImageList.md) メンバー関数を使用してリストを関連付けます。  既定では、すべての Itemspec と nonselected 状態のイメージ リストの最初のイメージが表示されます。  指定 nonselected とイメージのインデックスを指定して特定のアイテムの既定の動作を変更する項目を [InsertItem](../Topic/CTreeCtrl::InsertItem.md) メンバー関数を使用して、ツリー コントロールに追加します。  アイテムを追加した後 [SetItemImage](../Topic/CTreeCtrl::SetItemImage.md) メンバー関数を使用してインデックスを変更できます。  
  
 ツリー コントロールのイメージ リストは項目イメージに重なって表示されるように設計されたオーバーレイ イメージを含めることができます。  8 ビットからツリー コントロール項目の状態の 11 0 以外の値はオーバーレイ イメージのインデックス番号が 1 から始まるなインデックス \(0 はオーバーレイ イメージを参照\)。  4 ビットは、インデックス番号が 1 から始まるなインデックス使用されるため、オーバーレイ イメージは、イメージ リスト内の最初の 15 イメージの間にする必要があります。  ツリー ビュー コントロールのアイテムの状態に関する詳細については、このトピックの前半で [ツリー コントロール項目 States overview](../mfc/tree-control-item-states-overview.md) を参照します。  
  
 状態イメージ リストを指定すると、状態イメージの各項目のアイコンの左側にツリー コントロールの確保します。  アプリケーションは、定義済みの項目のステータスを示すステータス イメージをチェックされ、チェック ボックスをオフにするのも使用できます。  12 ~ 15 ビットの 0 以外の値は状態イメージのインデックス番号が 1 から始まるなインデックス \(0 は状態イメージを参照\)。  
  
 イメージのインデックスの代わりに **I\_IMAGECALLBACK** 値を指定して、項目が再描画される予定のまで指定または nonselected イメージを指定することもできます。  **I\_IMAGECALLBACK** は [TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) 通知メッセージを送信することによってインデックスのアプリケーションを照会するには、ツリー コントロールに指示します。  
  
 [GetImageList](../Topic/CTreeCtrl::GetImageList.md) のメンバー関数では、ツリー コントロールのイメージ リストのハンドルを取得します。  この関数は、リストにイメージを追加する必要がある場合に便利です。  イメージ リストの詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の *" MFC リファレンス"*の [CImageList を使用する](../mfc/using-cimagelist.md)、[CImageList](../Topic/CImageList%20Class.md)、[イメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb761389) を参照します。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)