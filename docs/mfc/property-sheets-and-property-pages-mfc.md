---
title: "プロパティ シートとプロパティ ページ (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 877d83a6833b9505c326bc5312d2f151add07cb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-and-property-pages-mfc"></a>プロパティ シートとプロパティ ページ (MFC)
MFC [ ダイアログ ボックス](../mfc/dialog-boxes.md)プロパティ シートとプロパティ ページを組み込むことにより実行できます。"タブ ダイアログ"を確認します。 正面や、重ねて表示されたウィンドウのグループから見たファイル フォルダーのスタックと同様に、タブ付きのシートのスタックを格納する「プロパティ シート」と呼ばれる、MFC では、この種のダイアログ ボックスで、Microsoft Word、Excel、および Visual C は、多くのダイアログ ボックスに似ていますが表示されます。 前面のタブ上のコントロールが表示されます。ラベルの付いたタブだけでは、背面のタブに表示されます。 プロパティ シートは、特に多数のプロパティまたは複数のグループに分類できる設定を管理するのに役立ちます。 通常、1 つのプロパティ シートは、いくつかの別のダイアログ ボックスを置き換えることで、ユーザー インターフェイスを簡素化できます。  
  
 プロパティ シートとプロパティ ページには、MFC バージョン 4.0 の時点でに Windows 95 および Windows NT version 3.51 以降に付属している共通コントロールを使用して実装されます。  
  
 プロパティ シートがクラスで実装される[CPropertySheet](../mfc/reference/cpropertysheet-class.md)と[CPropertyPage](../mfc/reference/cpropertypage-class.md) (で説明されている、 *『 MFC リファレンス*)。 `CPropertySheet`に基づいて"複数"ページを含めることができますの全体的なダイアログ ボックスの定義`CPropertyPage`です。  
  
 プロパティ シートの作成と操作については、トピックを参照してください。[プロパティ シート](../mfc/property-sheets-mfc.md)です。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)   
 [プロパティ シートとプロパティ ページ (MFC の)](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [データを交換します。](../mfc/exchanging-data.md)   
 [モードレス プロパティ シートの作成](../mfc/creating-a-modeless-property-sheet.md)   
 [[適用] ボタンの処理](../mfc/handling-the-apply-button.md)

