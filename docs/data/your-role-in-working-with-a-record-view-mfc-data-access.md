---
title: "レコード ビューを利用するために必要な作業 (MFC データ アクセス) | Microsoft Docs"
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
  - "MFC, レコード ビュー"
  - "レコード ビュー, カスタマイズ (既定のコードを)"
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコード ビューを利用するために必要な作業 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、レコード ビューを使用するために通常必要となる作業と、フレームワークの役割を示しています。  
  
### レコード ビューの使用: プログラマとフレームワーク  
  
|プログラマの役割|フレームワークの役割|  
|--------------|----------------|  
|Visual C\+\+ ダイアログ エディターを使用して、フォームをデザインします。|コントロール付きのダイアログ テンプレート リソースを作成します。|  
|[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)を使用して、[CRecordView](../mfc/reference/crecordview-class.md) および [CRecordset](../Topic/CRecordset%20Class.md)、または [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) および [CDaoRecordset](../mfc/reference/cdaorecordset-class.md) の派生クラスを作成します。|派生クラスを作成します。|  
|レコード ビューのコントロールをレコードセットのフィールド データ メンバーに対応付けます。|コントロールとレコードセット フィールド間で DDX を行います。|  
||メニューまたはツール バー ボタンから起動される **Move First**、**Move Last**、**Move Next**、および **Move Previous** の各コマンドに対する既定のコマンド ハンドラーを提供します。|  
||データ ソースへの変更を反映します。|  
|\(省略可能\) リスト ボックス、コンボ ボックスなどのコントロールにセカンド レコードセットのデータを設定するためのコードを記述します。||  
|\(省略可能\) 特別な検証用のコードを記述します。||  
|\(省略可能\) レコードを追加または削除するためのコードを記述します。||  
  
 フォーム ベースのプログラミングは、データベース操作の単なる 1 つの手法です。  その他のユーザー インターフェイスを利用するアプリケーション、またはユーザー インターフェイスのないアプリケーションの詳細については、「[MFC: ドキュメントとビューを用いたデータベース クラスの使用](../data/mfc-using-database-classes-with-documents-and-views.md)」および「[MFC: ドキュメントとビューを用いないデータベース クラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。  データベース レコードを表示する別の方法については、「[CListView](../mfc/reference/clistview-class.md)」クラスおよび「[CTreeView](../mfc/reference/ctreeview-class.md)」クラスを参照してください。  
  
## 参照  
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)