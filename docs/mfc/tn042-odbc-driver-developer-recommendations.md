---
title: "テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データベース [C++], ODBC"
  - "ODBC ドライバー [C++], 書き込み"
  - "TN042"
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 42: ODBC ドライバーの開発に関する推奨事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、ODBC ドライバー ライターのガイドラインを示します。  このサンプルは、MFC データベース クラスを変更して、さまざまな予期される意味詳細ついて説明します。ODBC の機能の一般的な要件と仮定します。  `CRecordset` の 3 種類のオープン モード \(**forwardOnly**、**スナップショット** と **ダイナセット**\) をサポートする必須ドライバーの機能について説明します。  
  
## ODBC カーソル ライブラリ  
 MFC データベース クラスには、多くの場合、ほとんどのレベル 1 の ODBC ドライバーによって提供される機能以外に、ユーザーによる操作を示します。  しかし、ODBC カーソル ライブラリは、データベース クラスとドライバーの間にレイヤーに、自動的にこの追加の多くの機能を提供します。  
  
 たとえば、ほとんどは 1.0 ドライバーへのスクロールをサポートしていません。  カーソル ライブラリはこれを調べ、ドライバーの行をキャッシュし、**SQLExtendedFetch**の FETCH\_PREV の呼び出しで要求されるようにします。  
  
 カーソル ライブラリの依存のもう一つの重要な例は位置指定更新です。  ほとんども 1.0 ドライバー位置指定更新はありませんが、カーソル ライブラリは現在のキャッシュされたデータ値に基づいてデータ ソースの対象の行を識別する、またはキャッシュ タイムスタンプ値を生成して UPDATE ステートメント。  
  
 クラス ライブラリには、複数の行セットを使用しません。  したがって、行セットの 1 を整列するために、**SQLSetPos** のステートメントが常に適用されます。  
  
## CDatabases  
 各 `CDatabase` は単一の **HDBC**を割り当てます。`CDatabase``ExecuteSQL` 関数を使用すると、**HSTMT** は一時的に割り当てられます。\) したがって、複数の entity\_CODECDatabase が必要な場合は、**HENV** ごとに複数の **HDBC**s をサポートする必要があります。  
  
 データベース クラスは、カーソル ライブラリを読み込む必要があります。  これは **SQLSetConnections** の呼び出し **SQL\_ODBC\_CURSORS**、**SQL\_CUR\_USE\_ODBC**に反映されます。  
  
 `CDatabase::Open` で**SQLDriverConnect**、**SQL\_DRIVER\_COMPLETE** がデータ ソースへの接続を確立するために使用されます。  
  
 ドライバーは **SQLGetInfo SQL\_ODBC\_API\_CONFORMANCE** \>\= **SQL\_OAC\_LEVEL1**、**SQLGetInfo SQL\_ODBC\_SQL\_CONFORMANCE** \>\= **SQL\_OSC\_MINIMUM**をサポートする必要があります。  
  
 `CDatabase` と依存するレコードセットでサポートされるトランザクションに **SQLGetInfo SQL\_CURSOR\_COMMIT\_BEHAVIOR** と **SQL\_CURSOR\_ROLLBACK\_BEHAVIOR** は **SQL\_CR\_PRESERVE**が必要です。  それ以外の場合は、トランザクションのコントロールを実行すると、無視されます。  
  
 **SQLGetInfo SQL\_DATA\_SOURCE\_READ\_ONLY** をサポートする必要があります。  これは「Y」が返された場合、更新操作がデータ ソースで実行されません。  
  
 開いている `CDatabase` が読み取り専用の場合は、データ ソースをそれぞれ設定しようとすると、**SQLSetConnectOption SQL\_ACCESS\_MODE**、**SQL\_MODE\_READ\_ONLY**でのみ行います。  
  
 識別子が引用符を必要とする場合は、この情報は **SQLGetInfo SQL\_IDENTIFIER\_QUOTE\_CHAR** を呼び出してドライバーから返されます。  
  
 デバッグのために、**SQLGetInfo SQL\_DBMS\_VER** と **SQL\_DBMS\_NAME** はドライバーから取得されます。  
  
 **SQLSetStmtOption SQL\_QUERY\_TIMEOUT** と **SQL\_ASYNC\_ENABLE** は `CDatabase`**HDBC**なる場合があります。  
  
 **SQLError** は 一部またはすべての引数の空白と呼ばれることもあります。  
  
 もちろん、**SQLAllocEnv**、**SQLAllocConnect**、**SQLDisconnect** と **SQLFreeConnect** をサポートする必要があります。  
  
## ExecuteSQL  
 一時 **HSTMT**を割り当ておよび解放するだけでなく、`ExecuteSQL` は **SQLExecDirect**、**SQLFetch**、**SQLNumResultCol** と `SQLMoreResults`を呼び出します。  **SQLCancel** は **HSTMT**なる場合があります。  
  
## GetDatabaseName  
 **SQLGetInfo SQL\_DATABASE\_NAME** が呼び出されます。  
  
## BeginTrans、CommitTrans のロールバック  
 トランザクションの要求が行われた場合**SQLSetConnectOption SQL\_AUTOCOMMIT** と **SQLTransact SQL\_COMMIT**、**SQL\_ROLLBACK** と **SQL\_AUTOCOMMIT** が呼び出されます。  
  
## CRecordsets  
 **SQLAllocStmt**、**SQLPrepare**、**SQLExecute** \(**開く** と **再クエリ**の場合\)、**SQLExecDirect** \(更新操作のために、**SQLFreeStmt**\) をサポートする必要があります。  **SQLNumResultCols** と **SQLDescribeCol** は結果セットを複数回呼び出されます。  
  
 **SQLSetParam** は バインディング パラメーター データと **DATA\_AT\_EXEC** メカニズムで広く使用されています。  
  
 **SQLBindCol** が ODBC の出力列のデータ ストレージの場所を登録するために広く使用されています。  
  
 **SQLGetData** の 2 回の呼び出しが **SQL\_LONG\_VARCHAR** と **SQL\_LONG\_VARBINARY** データを取得するために使用されます。  0 の cbMaxValue で、有効な pcbValue で **SQLGetData** を呼び出して、列の値の合計を検索し、最初の呼び出しを試みます。  pcbValue が **SQL\_NO\_TOTAL**を保持すると、例外がスローされます。  それ以外の場合は `HGLOBAL` が割り当てられ、全体的な結果を取得するに **SQLGetData** の他の呼び出しが行われました。  
  
## 更新  
 排他的なロックが要求された場合、**SQLGetInfo SQL\_LOCK\_TYPES** が呼び出されます。  **SQL\_LCK\_EXCLUSIVE** がサポートされていない場合、例外がスローされます。  
  
 `CRecordset` を更新すると、**スナップショット** または **ダイナセット** \(秒\) **HSTMT** を割り当てます。  2 番目の **HSTMT**をサポートしないドライバーの場合は、カーソル ライブラリはこの機能をシミュレートします。  ただし、これは、完了まで **HSTMT** の 2 番目の要求を処理する前に、最初の **HSTMT** の現在のクエリを強制する可能性もあります。  
  
 **SQLFreeStmt SQL\_CLOSE** と **SQL\_RESET\_PARAMS** と **SQLGetCursorName** は更新操作時に呼び出されます。  
  
 **outputColumns**に **CLongBinarys** がある場合は、ODBC の **DATA\_AT\_EXEC** の機能をサポートする必要があります。  これは、**SQLExecDirectSQLParamData** と **SQLPutData**から返される **SQL\_NEED\_DATA** が含まれます。  
  
 **SQLRowCount** は 1 レコードのみ **SQLExecDirect**によって更新されたことを確認する実行の後に呼び出されます。  
  
## ForwardOnly のカーソル  
 **SQLFetch** のみ **移動** 操作できます。  **forwardOnly** のカーソルが更新をサポートしないことに注意してください。  
  
## スナップショット カーソル  
 スナップショット機能は **SQLExtendedFetch** サポートが必要です。  上で説明したように、ODBC カーソル ライブラリはドライバーが **SQLExtendedFetch**をいつサポートしない検出し、必要なサポート自体を提供します。  
  
 **SQLGetInfo**、**SQL\_SCROLL\_OPTIONS** は **SQL\_SO\_STATIC**をサポートする必要があります。  
  
## ダイナセットのカーソル  
 ダイナセットを開くために必要な最小サポート:を次に示します。  
  
 **SQLGetInfo**、**SQL\_ODBC\_VER** は「 \> 01 "を返します。  
  
 **SQLGetInfo**、**SQL\_SCROLL\_OPTIONS** は **SQL\_SO\_KEYSET\_DRIVEN**をサポートする必要があります。  
  
 **SQLGetInfo**、**SQL\_ROW\_UPDATES** は「Y」を返す必要があります。  
  
 **SQLGetInfo**、**SQL\_POSITIONED\_UPDATES** は **SQL\_PS\_POSITIONED\_DELETE** と **SQL\_PS\_POSITIONED\_UPDATE**をサポートする必要があります。  
  
 また、排他的なロックを要求された場合は false irow 1、および fRefresh 群 **SQL\_LCK\_EXCLUSIVE** で **SQLSetPos** への呼び出しが行われました。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)