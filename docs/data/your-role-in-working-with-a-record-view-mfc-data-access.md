---
title: "レコード ビュー (MFC データ アクセス) の操作でロール |Microsoft ドキュメント"
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
- record views, customizing default code
- MFC, record views
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03d64715f3bdfb6028fdb039451d4b4b004a059e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="your-role-in-working-with-a-record-view--mfc-data-access"></a>レコード ビューを利用するために必要な作業 (MFC データ アクセス)
次の表は、レコード ビューを使用するために通常必要となる作業と、フレームワークの役割を示しています。  
  
### <a name="working-with-a-record-view-you-and-the-framework"></a>レコード ビューの使用: プログラマとフレームワーク  
  
|プログラマの役割|フレームワークの役割|  
|---------|-------------------|  
|Visual C++ ダイアログ エディターを使用して、フォームをデザインします。|コントロール付きのダイアログ テンプレート リソースを作成します。|  
|使用して、 [MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)から派生したクラスを作成する[CRecordView](../mfc/reference/crecordview-class.md)と[CRecordset](../mfc/reference/crecordset-class.md)です。|派生クラスを作成します。|  
|レコード ビューのコントロールをレコードセットのフィールド データ メンバーに対応付けます。|コントロールとレコードセット フィールド間で DDX を行います。|  
||既定のコマンド ハンドラーを提供**Move First**、 **Move Last**、 **Move Next**、および**Move Previous**メニューまたはツールバーのコマンドボタン。|  
||データ ソースへの変更を反映します。|  
|(省略可能) リスト ボックス、コンボ ボックスなどのコントロールにセカンド レコードセットのデータを設定するためのコードを記述します。||  
|(省略可能) 特別な検証用のコードを記述します。||  
|(省略可能) レコードを追加または削除するためのコードを記述します。||  
  
 フォーム ベースのプログラミングは、データベース操作の単なる 1 つの手法です。 その他のユーザー インターフェイスまたはユーザー インターフェイスのないを使用してアプリケーションについては、次を参照してください[MFC: ドキュメントとビューを用いたデータベース クラス](../data/mfc-using-database-classes-with-documents-and-views.md)と[MFC: 用いないデータベース クラスとビュー。](../data/mfc-using-database-classes-without-documents-and-views.md). データベース レコードを表示するための代替アプローチは、クラスを参照してください。 [CListView](../mfc/reference/clistview-class.md)と[CTreeView](../mfc/reference/ctreeview-class.md)です。  
  
## <a name="see-also"></a>参照  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)