---
title: "DAO と ODBC の相違 | Microsoft Docs"
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
  - "DAO (データ アクセス オブジェクト), および ODBC"
  - "ODBC, 概要 (ODBC の)"
ms.assetid: 22cc2f75-7ff6-47bc-ac56-56a40591104c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO と ODBC の相違
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ アクセス オブジェクト \(DAO: Data Access Objects\) と ODBC \(Open Database Connectivity\) は API です。この API を使用すると、特定のデータベース管理システム \(DBMS: Database Management System\) に依存しないアプリケーションを作成できます。  
  
 DAO は Microsoft Access Basic や Microsoft Visual Basic を使うデータベース プログラマによく知られています。  DAO は、Microsoft Jet データベース エンジンを使って、データベース オブジェクト、tabledef オブジェクト、querydef オブジェクト、レコードセット オブジェクトなどのデータ アクセス オブジェクトを提供します。  DAO は、Microsoft Access で作成した .mdb ファイルなどにアクセスする場合に最適ですが、Microsoft Jet データベース エンジンと組み合わせて ODBC データ ソースにアクセスすることもできます。  
  
 ODBC には、さまざまなデータベース販売元が、特定の DBMS に固有の ODBC ドライバーを使用して実装できる API が用意されています。  プログラムでは、この API を使って ODBC ドライバー マネージャーを呼び出し、適切なドライバーに呼び出しを渡します。  ドライバーは、SQL を使って DBMS と対話します。  
  
> [!NOTE]
>  ODBC は WOSA \(Microsoft Windows Open Standards Architecture\) の主要部分です。  DAO は Microsoft Jet データベース エンジンを中心に最適化されていますが、このエンジンを通じて ODBC を含む外部データ ソースにアクセスすることもできます。また、独立した ODBC API とこれに基づく MFC クラスも用意されていて、データベース ツールの選択にも使用されます。  
  
## 参照  
 [よく寄せられる質問 \- データ アクセス](../data/data-access-frequently-asked-questions-mfc-data-access.md)