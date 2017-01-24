---
title: "データ ソースへの接続 | Microsoft Docs"
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
  - "接続 [C++], データ ソース"
  - "データ ソース [C++], 接続"
  - "データベース接続 [C++], MFC ODBC クラス"
  - "データベース接続 [C++], ODBC"
  - "データベース [C++], 接続"
  - "ODBC 接続 [C++], 使用"
  - "ODBC データ ソース [C++], 接続"
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ ソースへの接続
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC データ ソースには、データのほかに、データにアクセスするための情報とデータの置かれている場所が含まれています。データ ソースは名前で参照できます。  プログラムから見たデータ ソースは、データ、DBMS、ネットワーク \(リモートの場合\)、ODBC を含みます。  
  
 データ ソースのデータにアクセスするには、最初にデータ ソースと接続します。  この接続を通じてすべてのアクセスを行います。  
  
 データ ソースとの接続は、[CDatabase](../../mfc/reference/cdatabase-class.md) クラスにカプセル化されます。  データ ソースに `CDatabase` オブジェクトを接続すると、次の操作を実行できます。  
  
-   [レコードセット](../Topic/CRecordset%20Class.md)を作成してテーブルやクエリのレコードを選択します。  
  
-   [トランザクション](../../data/odbc/transaction-odbc.md)を管理します。バッチ処理したすべての更新を一度にデータ ソースにコミットするか、データ ソースが変更されないようにトランザクション全体をロールバックします。ただし、データ ソース側で、必要なレベルのトランザクションがサポートされている必要があります。  
  
-   直接 [SQL](../../data/odbc/sql.md) のステートメントを実行します。  
  
 データ ソースとの接続を使い終わったら、`CDatabase` オブジェクトを閉じて、そのまま破棄するかまたは別の接続に再利用します。  データ ソースとの接続の詳細については、「[データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)」を参照してください。  
  
## 参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)