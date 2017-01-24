---
title: "DAO と ODBC を使ってアクセスできるデータ ソース | Microsoft Docs"
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
  - "DAO [C++], データ ソースのデータ型"
  - "データ [C++], DAO"
  - "データ [C++], ODBC"
  - "データ アクセス [C++], DAO"
  - "データ ソース [C++], アクセス可能 (DAO と ODBC による)"
  - "データベース [C++], アクセス (DAO での)"
  - "FAQ [C++], アクセスできるデータベース"
  - "ODBC [C++], アクセスできるデータ ソース"
  - "ODBC データ ソース [C++], アクセス可能"
ms.assetid: c88abb45-526a-467a-a01b-d9396bd63236
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO と ODBC を使ってアクセスできるデータ ソース
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

どちらの MFC クラスを使用しても、広範な種類のデータ ソースにアクセスできるだけでなく、データ ソースに依存しないアプリケーションを作成できます。  
  
##  <a name="_core_databases_you_can_access_with_dao"></a> DAO を使ってアクセスできるデータベース  
 DAO と MFC DAO クラスを使ってアクセスできるデータ ソースは次のとおりです。  
  
-   Microsoft Access または Microsoft Visual Basic で作成した Microsoft Jet データベース エンジンの Version 1.x、2.x、および 3.0 を使用するデータベース。  
  
-   次を含むインストール可能な ISAM データベース。  
  
    -   dBASE III、dBASE IV、dBASE 5.0。  
  
    -   Paradox Version 3.x、4.x、5.x。  
  
-   Microsoft SQL Server、SYBASE SQL Server、ORACLE Server などを含む ODBC \(Open Database Connectivity\) データベース。  ODBC データベースにアクセスするには、アクセス先のデータベースに対応する ODBC ドライバーが必要です。  Visual C\+\+ のこのバージョンに含まれている ODBC ドライバー一覧、および他のドライバーを取得する方法については、「[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)」を参照してください。  
  
-   Microsoft Excel Version 3.0、4.0、5.0、および 7.0 のワークシート。  
  
-   Lotus WKS、WK1、WK3、および WK4 のスプレッドシート。  
  
-   テキスト ファイル。  
  
 DAO は、Microsoft Jet データベース エンジンで読み取ることができるデータベースで適切に使用できます。これには、ODBC データ ソースを除く上記のすべてのものが含まれます。  Microsoft Jet \(.MDB\) データベースに使うと、最高のパフォーマンスを得られます。  外部テーブル \(特に ODBC データ ソースのテーブル\) は、MFC DAO クラスを通じて直接外部データベースを開くよりも、.mdb データベースにアタッチする方が効率的です。  
  
##  <a name="_core_databases_you_can_access_with_odbc"></a> ODBC を使ってアクセスできるデータベース  
 ODBC と MFC ODBC クラスでは、ユーザーのアプリケーションの ODBC ドライバーに対応したローカルまたはリモートのデータ ソースにアクセスできます。広範囲なデータ ソースに対して 16 ビット、32 ビット、および 64 ビットの ODBC ドライバーを使用できます。  Microsoft Jet \(.MDB\) データベースを使う場合は、Microsoft Access の ODBC ドライバーを使うよりも DAO クラスを使う方が効率的です。  
  
## 参照  
 [よく寄せられる質問 \- データ アクセス](../data/data-access-frequently-asked-questions-mfc-data-access.md)