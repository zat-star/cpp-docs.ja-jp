---
title: "コールバック項目とコールバック マスク |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24d9992b8a9db679b30624d85ede1a35bfd9826d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="callback-items-and-the-callback-mask"></a>コールバック項目とコールバック マスク
その項目のそれぞれについて、リスト ビュー コントロールが通常、ラベルのテキスト項目のアイコンのイメージ リスト インデックスを格納および項目の状態に対するフラグのビットのセット。 アプリケーションで既にがいくつかのアイテムの情報を保存する場合に便利ですが、コールバック項目として、個々 のアイテムを定義できます。  
  
 コールバック項目との適切な値を指定することで、項目を定義する、`pszText`と`iImage`のメンバー、 **LV_ITEM**構造 (を参照してください[CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem))。 アプリケーションが、項目のまたはサブ項目のテキストを保持する場合の指定、**保持するようにする**値を`pszText`メンバー。 アプリケーションの追跡項目のアイコン場合を指定する、**番号**値を`iImage`メンバー。  
  
 コールバック項目を定義するだけでなく、コントロールのコールバック マスクを変更することもできます。 このマスクは、対象のコントロールではなく、アプリケーションで現在のデータが格納する項目の状態を指定するビット フラグのセットです。 コールバック マスクは、すべての特定の項目に適用されるコールバック項目の指定とは異なり、コントロールの項目に適用されます。 コールバック マスクは、既定では、コントロールがすべての項目の状態を追跡することを意味する 0 です。 この既定の動作を変更するには、次の値の任意の組み合わせにマスクを初期化します。  
  
-   `LVIS_CUT`項目は、カット アンド ペースト操作がマークされます。  
  
-   `LVIS_DROPHILITED`アイテムがドラッグ アンド ドロップのターゲットとして強調表示されます。  
  
-   `LVIS_FOCUSED`項目にフォーカスが移動するとします。  
  
-   `LVIS_SELECTED`項目が選択されます。  
  
-   **LVIS_OVERLAYMASK**アプリケーションは、各項目の現在のオーバーレイ イメージのイメージ リスト インデックスを格納します。  
  
-   **LVIS_STATEIMAGEMASK**アプリケーションは、各アイテムの現在の状態のイメージのイメージ リスト インデックスを格納します。  
  
 取得して、このマスクの設定の詳細については、次を参照してください。 [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask)と[CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask)です。  
  
## <a name="see-also"></a>参照  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

