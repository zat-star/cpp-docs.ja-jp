---
title: "プロパティ シートとプロパティ ページ (MFC) | Microsoft Docs"
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
  - "CPropertyPage クラス, プロパティ シートとページ"
  - "CPropertySheet クラス, プロパティ シートとページ"
  - "MFC ダイアログ ボックス, タブ"
  - "プロパティ ページ, プロパティ シート"
  - "プロパティ シート, プロパティ ページ"
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# プロパティ シートとプロパティ ページ (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC [ダイアログ ボックス](../mfc/dialog-boxes.md) は「タブ ダイアログ ボックス」でプロパティ シートとプロパティ ページを組み込むことによって実行できます。  MFC の Microsoft Word、Excel の多数のダイアログ ボックスと同じように、この種類の「プロパティ シート」をダイアログ ボックスをサポートするための先頭から参照されるファイル フォルダーのスタックと同じように記録されたシートのスタックまたは連鎖"ようにするペインのグループを含む Visual C\+\+ は、などです。  詳細タブのコントロールが増えます; ラベル付きのタブがバックエンド タブに表示されます。  プロパティ シートは複数のグループに伴ってきれいにドロップした設定または多数のプロパティを管理する場合に特に便利です。  通常、1 種類のプロパティ シートは、複数の異なるダイアログ ボックスで置換することでユーザー インターフェイスを簡略化できます。  
  
 MFC 4.0 以降では、プロパティ シートとプロパティ ページは、Windows 95 および Windows NT 3.51 以降であるコモン コントロールを使用して実装されます。  
  
 プロパティ シートは、クラス [CPropertySheet](../mfc/reference/cpropertysheet-class.md) と [CPropertyPage](../mfc/reference/cpropertypage-class.md) と実装されます \(*MFC の*"で説明されている\)。  `CPropertySheet` は `CPropertyPage`に基づいて複数の「ページ」を含めることができる全体的なダイアログ ボックスを定義します。  
  
 プロパティ シートの作成と使用の詳細については、" [プロパティ シート](../mfc/property-sheets-mfc.md)を参照してください。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)   
 [MFC のプロパティ シートとプロパティ ページ](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [データの交換](../mfc/exchanging-data.md)   
 [モードレス プロパティ シートの作成](../mfc/creating-a-modeless-property-sheet.md)   
 [\[適用\] ボタンの処理](../Topic/Handling%20the%20Apply%20Button.md)