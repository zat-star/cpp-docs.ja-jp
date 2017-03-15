---
title: "レコード ビュー (MFC データ アクセス) | Microsoft Docs"
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
  - "DAO [C++], レコード ビュー"
  - "データベース [C++], レコード ビュー"
  - "フォーム [C++], データ アクセス タスク"
  - "MFC [C++], レコード ビュー"
  - "ODBC レコードセット [C++], レコード ビュー"
  - "レコード ビュー [C++]"
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード ビュー (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このセクションは、MFC ODBC クラスと DAO クラスにのみ適用されます。  OLE DB レコード ビューの詳細については、「[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)」および「[OLE DB レコード ビューの使用](../data/oledb/using-ole-db-record-views.md)」を参照してください。  
  
 フォーム ベースのデータ アクセス アプリケーションをサポートするために、クラス ライブラリには [CRecordView](../mfc/reference/crecordview-class.md) クラスおよび [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) クラスが用意されています。  レコード ビューは、フォーム ビュー オブジェクトの一種であり、そのコントロールは [recordset](../data/odbc/recordset-odbc.md) オブジェクトのフィールド データ メンバーに直接対応付けられています \(また、クエリ結果またはデータ ソースのテーブルの対応する列に間接的に対応付けられています\)。  基本クラス [CFormView](../mfc/reference/cformview-class.md) と同様、`CRecordView` および `CDaoRecordView` はダイアログ テンプレート リソースに基づきます。  
  
## フォームの利用  
 フォームは、さまざまなデータ アクセス タスクに使用できます。  
  
-   データの入力  
  
-   データが読み取り専用かどうかの検証の実行  
  
-   データの更新  
  
## レコード ビューについての詳細情報  
 トピックの内容は、ODBC ベースのクラスおよび DAO ベースのクラスに共通して適用されます。  ODBC の場合は `CRecordView` を、DAO の場合は `CDaoRecordView` を使用します。  
  
 ここでは、次の内容について説明します。  
  
-   [レコード ビュー クラスの機能](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [レコード ビューのデータ交換](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [レコード ビューを利用するために必要な作業](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [レコード ビューのデザインと作成](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)  
  
## 参照  
 [データ アクセス プログラミング \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)