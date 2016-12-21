---
title: "データ ソース (ODBC) | Microsoft Docs"
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
  - "CDatabase クラス, データ ソース接続"
  - "構成 (ODBC データ ソースを)"
  - "ODBC データ ソース"
  - "ODBC データ ソース, 構成"
  - "ODBC データ ソース, 表現 (CDatabase による)"
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ ソース (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 データベース用語では、データ ソースは、データの集合、そのデータにアクセスするための情報、およびデータ ソースの位置で構成され、データ ソース名で参照できます。  [CDatabase](../../mfc/reference/cdatabase-class.md) クラスを使うには、対象となるデータ ソースが ODBC \(Open Database Connectivity\) アドミニストレーターによって設定されている必要があります。  データ ソースの例としては、ネットワーク上の Microsoft SQL Server で実行中のリモート データベースや、ローカル ディレクトリにある Microsoft Access のファイルなどがあります。  アプリケーションからは、ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでもアクセスできます。  
  
 アプリケーションでは、同時に複数のデータ ソースをアクティブにし、各データ ソースをそれぞれ別の `CDatabase` オブジェクトで表すことができます。  また、どのデータ ソースにも同時に複数の接続を確立できます。  インストールされている ODBC ドライバーの機能によっては、ローカルだけでなくリモートのデータ ソースにも接続できます。  データ ソースと ODBC データ ソース アドミニストレーターの詳細については、「[ODBC の基礎](../../data/odbc/odbc-basics.md)」および「[ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)」を参照してください。  
  
 データ ソースの詳細については、次のトピックを参照してください。  
  
-   [データ ソース : 接続 \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [データ ソース : データ ソースのスキーマの判定 \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)