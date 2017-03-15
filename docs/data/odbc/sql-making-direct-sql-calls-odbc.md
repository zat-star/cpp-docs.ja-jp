---
title: "SQL: SQL の直接呼び出し (ODBC) | Microsoft Docs"
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
  - "直接呼び出し (ODBC から SQL を)"
  - "ODBC, SQL 呼び出し"
  - "SQL 呼び出し"
  - "SQL, 呼び出し (ODBC から直接に)"
  - "SQL, 直接呼び出し (ODBC からの)"
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SQL: SQL の直接呼び出し (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、次の内容について説明します。  
  
-   SQL を直接呼び出す場合  
  
-   [SQL 関数を直接呼び出す方法](#_core_making_direct_sql_function_calls)  
  
> [!NOTE]
>  この内容は、MFC ODBC クラスに該当します。  MFC DAO クラスを使用している場合は、DAO ヘルプの「Comparison of Microsoft Jet Database Engine SQL and ANSI SQL」を参照してください。  
  
##  <a name="_core_when_to_call_sql_directly"></a> SQL を直接呼び出す場合  
 テーブルの新規作成、削除、変更、インデックスの作成など、[データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)のスキーマを変更するような SQL 関数を利用するときは、DDL \(Database Definition Language\) を使って、SQL ステートメントを直接データ ソースに発行します。  ウィザードを使ってレコードセットを作成すると、レコードセットに含める列をアプリケーションのデザイン時に指定できます。  ただし、この方法では、アプリケーションの作成後にテーブルに追加された列にアクセスできません。  データベース クラスでは DDL が直接サポートされていませんが、新しく追加された列をレコードセットに動的に \(プログラム実行時に\) 結び付ける方法があります。  このバインディングを行う方法については、「[レコードセット: データ列を動的に結びつける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。  
  
 DBMS 自体を使ってスキーマを更新することも、DDL 関数を実行するツールを使用することもできます。  ODBC 関数を呼び出して SQL ステートメントを送ることもできます。この場合は、レコードを返さない定義済みクエリ \(ストアド プロシージャ\) などを呼び出すことができます。  
  
##  <a name="_core_making_direct_sql_function_calls"></a> SQL 関数を直接呼び出す方法  
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md) オブジェクトを使って SQL を直接呼び出すことができます。  SQL ステートメント文字列 \(通常は `CString`\) を作成し、この文字列を `CDatabase` オブジェクトのメンバー関数 [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) に渡します。  ODBC 関数を呼び出して SQL ステートメントを送ると、通常レコードを返すステートメントであってもレコードは無視されます。  
  
## 参照  
 [SQL](../../data/odbc/sql.md)