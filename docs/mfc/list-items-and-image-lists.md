---
title: "リスト項目とイメージ リスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 525d8353c308796d70f974fa56cde3aa76c12142
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="list-items-and-image-lists"></a>リスト項目とイメージ リスト
リスト コントロールの"item"([CListCtrl](../mfc/reference/clistctrl-class.md))、アイコン、ラベル、および可能性のある他の情報 (「サブ項目」) で構成されます。  
  
 リスト コントロール項目のアイコンは、イメージ リストに格納されます。 1 つのイメージ リストには、アイコン表示で使用されているフル サイズのアイコンが含まれています。 2 番目、省略可能、イメージの一覧には、コントロールの他のビューで使用する同じアイコンの縮小版が含まれています。 3 番目の省略可能な一覧には、特定のビューに小さいアイコンの前に表示するためのチェック ボックスなどの"state"イメージが含まれています。 4 番目の省略可能な一覧には、リスト コントロールの個々 のヘッダー項目に表示されるイメージが含まれています。  
  
> [!NOTE]
>  リスト ビュー コントロールが作成された場合、`LVS_SHAREIMAGELISTS`スタイルを使用するには不要になったときに、イメージ リストを破棄します。 複数のリスト ビュー コントロールを同じイメージを割り当てる場合は、このスタイルの一覧を指定します。それ以外の場合、複数のコントロールは同じイメージのリストを破棄しよう可能性があります。  
  
 リスト項目の詳細については、次を参照してください。[リスト ビューのイメージ リスト](http://msdn.microsoft.com/library/windows/desktop/bb774736)と[アイテムとサブアイテム](http://msdn.microsoft.com/library/windows/desktop/bb774736)Windows SDK にします。 クラスを参照して[CImageList](../mfc/reference/cimagelist-class.md)で、 *『 MFC リファレンス*と[を使用して CImageList](../mfc/using-cimagelist.md)この一連のトピックでします。  
  
 リスト コントロールを作成するには、一覧に新しい項目を挿入するときに使用されるイメージ リストを提供する必要があります。 次の例では、この手順では、ここで`m_pImagelist`型のポインターは、`CImageList`と`m_listctrl`は、`CListCtrl`データ メンバーです。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 ただし、リスト ビューまたはリスト コントロールにアイコンを表示する予定がない場合は、イメージ リストを必要ありません。  
  
## <a name="see-also"></a>参照  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

