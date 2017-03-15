---
title: "テクニカル ノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN068"
  - "トランザクション, 呼び出し (BeginTrans を)"
  - "トランザクション, Microsoft Access"
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テクニカル ノート 68: Microsoft Access 7 ODBC ドライバーでのトランザクションの実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、MFC ODBC データベース クラスを使用する場合、トランザクションを実行する方法について説明し、デスクトップ Microsoft ODBC ドライバーに含まれる Microsoft Access 7.0 の ODBC ドライバーは Version 3.0 をパックされます。  
  
## 概要  
 データベース アプリケーションでトランザクションを実行すると、アプリケーションの適切な順序で `CDatabase::BeginTrans` と `CRecordset::Open` を呼び出す必要があります。  Microsoft Access 7.0 ドライバーでの Microsoft Jet データベース エンジンを使用し、Jet はアプリケーション開かれているカーソルを持つすべてのデータベースのトランザクションが開始されて必要があります。  MFC の ODBC データベース クラスに、開かれているカーソルは、開いている `CRecordset` にオブジェクトと一致します。  
  
 **BeginTrans**を呼び出す前に、レコードセットを開いた場合は、エラー メッセージを参照しないことができます。  ただし、どのレコードセットでもアプリケーションを作成 `CRecordset::Update`を呼び出した後に永続的な更新し、**Rollback**を呼び出してロールバックされません。  この問題を回避するには、**BeginTrans** を最初に呼び出すと、レコードセットを開きます。  
  
 MFC は、カーソル、Rollback 動作の機能がコミット ドライバーをチェックします。  クラス `CDatabase` は `CRecordset` の開いているオブジェクトのトランザクションの影響を確認するための 2 種類のメンバー関数、`GetCursorCommitBehavior` と `GetCursorRollbackBehavior`を提供します。  Microsoft Access 7.0 ODBC ドライバーによっては、これらのメンバー関数はアクセス ドライバーがカーソルの保持をサポートしないため `SQL_CB_CLOSE` を返します。  したがって、**CommitTrans** または **Rollback** 操作を続行 `CRecordset::Requery` を呼び出す必要があります。  
  
 複数のトランザクションを順次実行する必要がある場合は、最初のトランザクションの後に **再クエリ** を呼び出して次の 1 を開始することはできません。  **BeginTrans** に Jet の要件を満たすために、レコードセットを閉じる前に復元する必要があります。  このテクニカル ノートはこの状況を処理する 2 種類のメソッドについて説明します。:  
  
-   **CommitTrans** または **Rollback** 各操作後のレコードセットを閉じたとき。  
  
-   ODBC API 関数の **SQLFreeStmt**を使用します。  
  
## CommitTrans または Rollback 各操作後のレコードセットを閉じたとき  
 トランザクションを開始する前に、レコードセット オブジェクトが閉じていることを確認します。  **BeginTrans**を呼び出した後、レコードセットの **開く** メンバー関数を呼び出します。  **CommitTrans** または **Rollback**を呼び出した直後のレコードセットを閉じます。  繰り返しレコードセットを開いたり閉じたりするとアプリケーションのパフォーマンスが低下する可能性があることに注意してください。  
  
## SQLFreeStmt を使用する  
 明示的にトランザクションが終了したらカーソルを閉じるには、ODBC API 関数の **SQLFreeStmt** を使用できます。  別のトランザクションを開始するには、**BeginTrans** を `CRecordset::Requery`が従うから呼び出します。  **SQLFreeStmt**を呼び出した場合、最初のパラメーターとして、レコードセットの HSTMT と 2 番目のパラメーターとして **SQL\_CLOSE** を指定する必要があります。  このメソッドは、そのトランザクションの開始時に終了と開始高速です\)。  次のコードは、このテクニックを実装する方法について説明します。:  
  
```  
CMyDatabase db;  
db.Open( "MYDATASOURCE" );  
CMyRecordset rs( &db );  
  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor  
::SQLFreeStmt( rs.m_hstmt, SQL_CLOSE );  
  
// start transaction 2  
db.BeginTrans( );  
  
// now get the result set  
rs.Requery( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  
  
rs.Close( );  
db.Close( );  
```  
  
 この手法を実装するもう一つの方法は、ロールバック最初のブックマーク コミットすると新しい関数、次のトランザクションを開始するために呼び出すことができる **RequeryWithBeginTrans**を記述することです。  このような関数を記述するには、次の手順を行う:  
  
1.  新しい関数に **CRecordset::Requery\( \)** のコードをコピーします。  
  
2.  **SQLFreeStmt**の呼び出しの直後に次の行を追加する:  
  
     `m_pDatabase->BeginTrans( );`  
  
 これで、トランザクションの各ペア間のこの関数を呼び出すことができますが、T:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor, start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  // or Rollback( )  
```  
  
> [!NOTE]
>  トランザクション中のレコードセットのメンバー変数 **m\_strFilter** または `m_strSort` を変更する必要がある場合は、この手法を使用しないでください。  この場合、**CommitTrans** または **Rollback** 各操作によってレコードセットを閉じる必要があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)