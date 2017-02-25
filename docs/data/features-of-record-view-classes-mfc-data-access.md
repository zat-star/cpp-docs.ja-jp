---
title: "レコード ビュー クラスの機能 (MFC データ アクセス) | Microsoft Docs"
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
  - "レコード ビュー クラス"
  - "レコード ビュー, クラス"
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード ビュー クラスの機能 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フォーム ベースのデータ アクセス プログラミングは、[CFormView](../mfc/reference/cformview-class.md) を使用して行うことができます。ただし、通常はその派生クラスである [CRecordView](../mfc/reference/crecordview-class.md) および [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) の使用をお勧めします。  `CFormView` の機能以外に、`CRecordView` および `CDaoRecordView` には次の機能が用意されています。  
  
-   フォーム コントロールと関連するレコードセット オブジェクト間のダイアログ データ エクスチェンジ \(DDX\)  
  
-   Move First、Move Next、Move Previous、および Move Last の各コマンドの処理による、関連するレコードセット オブジェクト内のレコード間の移動  
  
-   ユーザーが別のレコードに移動したときの、現在のレコードへの変更の反映  
  
 ナビゲーションの詳細については、「[レコード ビュー: レコード ビュー内のナビゲーションのサポート](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)」を参照してください。  
  
## 参照  
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)