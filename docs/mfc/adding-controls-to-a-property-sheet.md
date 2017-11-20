---
title: "プロパティ シートへのコントロールの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5623f95a77710e0ffbfa8a444de6f569f24105e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>プロパティ シートへのコントロールの追加
既定では、プロパティ シートは、プロパティ ページ、タブ インデックス、および、ok、キャンセル、適用ボタンをウィンドウ領域を割り当てます。 (モードレス プロパティ シートが [ok]、キャンセル、およびボタンを適用します。)プロパティ シートには、その他のコントロールを追加できます。 たとえば、現在の設定は外部のオブジェクトに適用される場合のようになりますが、ユーザーを表示するプロパティ ページの領域の右側にプレビュー ウィンドウを追加できます。  
  
 プロパティ シート ダイアログ ボックスにコントロールを追加することができます、`OnCreate`ハンドラー。 その他のコントロールに通常対応するには、プロパティ シート ダイアログ ボックスのサイズを拡張する必要があります。 基本クラスの呼び出し後に**CPropertySheet::OnCreate**、呼び出す[GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect)現在割り当てられているプロパティ シート ウィンドウの高さと幅を取得するには、展開、四角形のディメンション、および呼び出し[MoveWindow](../mfc/reference/cwnd-class.md#movewindow)プロパティ シート ウィンドウのサイズを変更します。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ シート](../mfc/property-sheets-mfc.md)   
 [CPropertyPage クラス](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet クラス](../mfc/reference/cpropertysheet-class.md)
