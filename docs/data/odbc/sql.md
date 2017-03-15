---
title: "SQL | Microsoft Docs"
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
  - "データベース クラス [C++], SQL ステートメント"
  - "ODBC [C++], SQL の実装"
  - "SQL [C++]"
  - "SQL [C++], ODBC"
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SQL \(Structured Query Language\) は、定義できるリレーショナル データベースと通信してデータのクエリと変更および制御する方法です。  SQL 構文でステートメントを記述すると、条件を指定してレコードを抽出できます。  
  
> [!NOTE]
>  この内容は、MFC ODBC クラスに該当します。  MFC DAO クラスを使用している場合は、DAO ヘルプの「Comparison of Microsoft Jet Database Engine SQL and ANSI SQL」を参照してください。  
  
 SQL ステートメントの先頭には必ず **CREATE** や **SELECT** などのキーワードとなる動詞を記述します。  SQL は、単一のステートメントでテーブル全体を操作できる強力な言語です。  
  
 SQL には多くのバージョンがあり、それぞれ特定の DBMS を対象に開発されています。  MFC データベース クラスは、X\/Open と SQL Access Group の CAE \(Common Applications Environment\) SQL ドラフト仕様 \(1991\) に準拠した SQL ステートメントを認識します。  これらのステートメントの構文については、MSDN ライブラリ CD の『ODBC Programmer's Reference』の「Appendix C: SQL Grammar」を参照してください。  
  
 このトピックでは、次の内容について説明します。  
  
-   [ODBC \(Open Database Connectivity\)](#_core_open_database_connectivity_.28.odbc.29)  
  
-   [データベース クラス](#_core_the_database_classes)  
  
-   [データベース クラスが SQL を利用するしくみ](#_core_how_the_database_classes_use_sql)  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> ODBC \(Open Database Connectivity\)  
 データベース クラスには ODBC が実装されています。ODBC では、呼び出しレベルのインターフェイスで SQL を使用するので、SQL コマンドをコードに埋め込みません。  ODBC は、SQL を使用し、ODBC ドライバーを通じて[データ ソース](../../data/odbc/data-source-odbc.md)とデータをやり取りします。  ODBC ドライバーは、SQL を解釈し、必要に応じて、特定のデータベース形式 \(Microsoft Access 形式など\) に変換します。  ODBC での SQL の使用方法の詳細については、「[ODBC の基礎](../../data/odbc/odbc-basics.md)」および MSDN ライブラリ CD の『ODBC Programmer's Reference』を参照してください。  
  
##  <a name="_core_the_database_classes"></a> データベース クラス  
 データベース クラスは、既存の[データ ソース](../../data/odbc/data-source-odbc.md)のデータを操作および更新できるようにデザインされています。  ほとんどの SQL ステートメントは、[MFC のアプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)、[MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md) \(クラスの追加から使用\)、およびデータベース クラスによって自動的に生成されます。  
  
 データベース クラスは、SQL 内の DML \(Data Manipulation Language\) と呼ばれる部分を使用します。  DML のコマンドで、データ ソースの一部または全体を操作することも、レコードを新規作成、編集、削除することもできます。  次の表に、主な SQL キーワードとデータベース クラスでの使い方を示します。  
  
### 主要な SQL キーワード  
  
|SQL キーワード|ウィザードとデータベース クラスにおける使い方|  
|---------------|-----------------------------|  
|**SELECT**|データ ソース内のテーブルと列を選択する。|  
|**WHERE**|選択範囲を限定するフィルターを指定する。|  
|**ORDER BY**|レコードセットの並べ替え順序を指定する。|  
|**Ins**|レコードセットに新規レコードを挿入する。|  
|**Del**|レコードセットからレコードを削除する。|  
|**UPDATE**|レコードのフィールド値を変更する。|  
  
 データベース クラスは、ODBC ステートメント **CALL** も認識します。このステートメントでは、一部のデータ ソースに対して定義済みクエリ \(ストアド プロシージャ\) を呼び出すことができます。  ODBC データベース ドライバーは、これらのステートメントを解釈し、各 DBMS 向けのコマンドに変換します。  
  
> [!NOTE]
>  **CALL** ステートメントをサポートしない DBMS もあります。  
  
 ユーザーが `CRecordset::Open` で指定したステートメントをデータベース クラスが認識できないと、そのステートメントはテーブル名と見なされます。  
  
 フレームワークでの SQL ステートメントの作成方法については、「[レコードセット : レコード選択のしくみ \(ODBC\)](../Topic/Recordset:%20How%20Recordsets%20Select%20Records%20\(ODBC\).md)」および「[SQL : レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)」を参照してください。  
  
 SQL データベースで使用するデータ型は、C および C\+\+ のデータ型に似ています。  詳細については、「[SQL : SQL と C\+\+ のデータ型 \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)」を参照してください。  
  
 SQL の詳細については、MSDN ライブラリ CD の『ODBC Programmer's Reference』を参照してください。使用できる SQL ステートメントおよびデータ型の一覧、SQL 文法の詳細、SQL の関連資料などがわかります。  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> データベース クラスが SQL を利用するしくみ  
 データベース クラスから派生したレコードセット クラスでは、ODBC を使ってデータ ソースとやり取りします。ODBC は、SQL ステートメントを送出してデータ ソースのレコードを取得します。  このトピックでは、データベース クラスと SQL の関係について説明します。  
  
 レコードセットは、SQL ステートメントの要素を 1 つの `CString` 文字列にまとめることによって、SQL ステートメントを構築します。  この文字列は、**SELECT** ステートメントとして構築され、一連のレコードを抽出します。  
  
 レコードセットが ODBC を呼び出してデータ ソースに SQL ステートメントを送ると、ODBC ドライバー マネージャーは、ステートメントを ODBC ドライバーに渡します。ODBC ドライバーは、このステートメントを DBMS に渡します。  DBMS が抽出したレコードを返すと、ODBC ドライバーは、このレコードをアプリケーションに返します。  アプリケーションのデータベース クラスは、レコードの値を `CRecordset` から派生したタイプ セーフな C\+\+ クラスに保存するので、プログラムからこれらの値にアクセスできます。  
  
 データベース クラスでの SQL の使用方法の詳細については、次のトピックを参照してください。  
  
-   [SQL : レコードセットの SQL ステートメントのカスタマイズ \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)  
  
-   [SQL : SQL と C\+\+ のデータ型 \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL : SQL の直接呼び出し \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)   
 [ODBC の基礎](../../data/odbc/odbc-basics.md)