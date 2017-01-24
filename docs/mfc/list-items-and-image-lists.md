---
title: "リスト項目とイメージ リスト | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CImageList クラス, およびリスト項目"
  - "CListCtrl クラス, イメージ リスト"
  - "イメージ リスト [C++], リスト項目"
  - "リスト項目, イメージ リスト"
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リスト項目とイメージ リスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リスト コントロール \([CListCtrl](../Topic/CListCtrl%20Class.md)\) の「Item」は、アイコン、ラベル、およびそのほかの情報で構成され \(「サブ項目で」\)。  
  
 リスト コントロール項目のアイコンのイメージ リストに含まれています。  1 種類のイメージ リストのアイコン ビューで使用される大きいアイコンなどが含まれます。  2 番目は、省略可能、コントロールの他のビューにイメージ リスト使用の同じアイコンの小さなバージョンが含まれています。  3 番目の省略可能なリストは特定のビューに「状態」イメージを、小さいアイコンの表示のチェック ボックスなど\) が含まれます。  4 番目の省略可能な一覧がリスト コントロールのヘッダー項目に表示されるイメージを示します。  
  
> [!NOTE]
>  リスト ビュー コントロールが `LVS_SHAREIMAGELISTS` のスタイルで作成されている場合、使用していないときは、イメージ リストの破棄する必要があります。  複数のリスト ビュー コントロールに同じイメージ リストを割り当てた場合、このスタイルを指定します。; それ以外の場合は、複数のコントロールが同じイメージ リストを破棄しようとする場合があります。  
  
 リスト項目の詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [リスト ビューのイメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb774736) と [項目とサブ項目](http://msdn.microsoft.com/library/windows/desktop/bb774736) を参照します。  、"ここの *MFC 参照* クラス [CImageList](../Topic/CImageList%20Class.md) と [CImageList を使用する](../mfc/using-cimagelist.md) を参照してください。  
  
 リストに新しい項目を挿入すると、リスト コントロールを作成するには、使用するイメージ リストを指定する必要があります。  次の例では `m_pImagelist` が型 `CImageList` ポインターである `m_listctrl` が `CListCtrl` のデータ メンバーであるこのプロシージャを示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/CPP/list-items-and-image-lists_1.cpp)]  
  
 ただし、リスト ビューまたはリスト コントロールのアイコンを表示することを計画するイメージ リストは必要ではありません。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)