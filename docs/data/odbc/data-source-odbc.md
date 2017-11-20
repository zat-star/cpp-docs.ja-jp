---
title: "データ ソース (ODBC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e0236c8684c37b0378dd7ebead37d2c9c44cf1d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="data-source-odbc"></a>データ ソース (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 データベース用語では、データ ソースは、データの集合、そのデータにアクセスするための情報、およびデータ ソースの位置で構成され、データ ソース名で参照できます。 クラスを使用する[CDatabase](../../mfc/reference/cdatabase-class.md)、データ ソースは、オープン データベース コネクティビティ (ODBC) の管理者によって設定されているいずれかを指定する必要があります。 データ ソースの例には、ネットワークまたはローカルのディレクトリ内の Microsoft Access ファイル全体で Microsoft SQL Server で実行されているリモートのデータベースが含まれます。 アプリケーションからは、ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでもアクセスできます。  
  
 アプリケーションでは、同時に複数のデータ ソースをアクティブにし、各データ ソースをそれぞれ別の `CDatabase` オブジェクトで表すことができます。 また、どのデータ ソースにも同時に複数の接続を確立できます。 インストールされている ODBC ドライバーの機能によっては、ローカルだけでなくリモートのデータ ソースにも接続できます。 データ ソースと odbc データ ソース アドミニストレーターの詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と[ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)です。  
  
 データ ソースの詳細については、次のトピックを参照してください。  
  
-   [データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [データ ソース: データ ソースのスキーマの判定 (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## <a name="see-also"></a>関連項目  
 [ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)