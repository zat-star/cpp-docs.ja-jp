---
title: "CDatabase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDatabase クラス"
  - "データベース クラス [C++], ODBC"
  - "データベース接続 [C++], CDatabase クラス"
  - "MFC [C++], ODBC"
  - "ODBC [C++], CDatabase クラス"
  - "ODBC データベース クラス"
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDatabase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースへの接続を表します。これを通じてデータ ソース上で操作を行うことができます。  
  
## 構文  
  
```  
  
class CDatabase : public CObject  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDatabase::CDatabase](../Topic/CDatabase::CDatabase.md)|`CDatabase` オブジェクトを構築します。  `OpenEx` か **\[開く\]**を呼び出してオブジェクトを初期化する必要があります。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDatabase::BeginTrans](../Topic/CDatabase::BeginTrans.md)|—接続されたデータ ソースのトランザクション「…」— `CRecordset` クラスの `AddNew`、**\[編集\]**、**\[削除\]**と **更新** のメンバー関数に一連の呼び出し元の開始します。  データ ソースは効果が得られるように **BeginTrans** のトランザクションをサポートする必要があります。|  
|[CDatabase::BindParameters](../Topic/CDatabase::BindParameters.md)|割り当て `CDatabase::ExecuteSQL`を呼び出す前にパラメーターへのバインド。|  
|[CDatabase::Cancel](../Topic/CDatabase::Cancel.md)|2 番目のスレッドからの非同期操作またはプロセスを取り消します。|  
|[CDatabase::CanTransact](../Topic/CDatabase::CanTransact.md)|データ ソースがトランザクションをサポートしている場合は、を返します。|  
|[CDatabase::CanUpdate](../Topic/CDatabase::CanUpdate.md)|`CDatabase` のオブジェクトが更新可能である場合は、を返します \(読み取り専用\)。|  
|[CDatabase::Close](../Topic/CDatabase::Close.md)|データ ソースの接続を閉じます。|  
|[CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md)|**BeginTrans**によって開始されたトランザクションが終了します。  データ ソースを変更するトランザクションのコマンドが実行されます。|  
|[CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)|SQL ステートメントを実行します。  データ レコードは返されません。|  
|[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)|ブックマークがレコードセット オブジェクトを永続化する操作を識別します。|  
|[CDatabase::GetConnect](../Topic/CDatabase::GetConnect.md)|データ ソースへの `CDatabase` のオブジェクトを接続するために使用される ODBC 接続文字列を返します。|  
|[CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md)|開いているレコードセット オブジェクトに対するトランザクションをコミット効果を識別します。|  
|[CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md)|開いているレコードセット オブジェクトのトランザクションをロールバック効果を識別します。|  
|[CDatabase::GetDatabaseName](../Topic/CDatabase::GetDatabaseName.md)|現在使用中のデータベースの名前を返します。|  
|[CDatabase::IsOpen](../Topic/CDatabase::IsOpen.md)|データ ソースへの `CDatabase` のオブジェクトが現在接続された場合、を返します。|  
|[CDatabase::OnSetOptions](../Topic/CDatabase::OnSetOptions.md)|標準的な接続オプションを設定するために、フレームワークによって呼び出されます。  既定の実装では、クエリ タイムアウト値を設定します。  `SetQueryTimeout`を呼び出して、これらのオプションを事前に設定できます。|  
|[CDatabase::Open](../Topic/CDatabase::Open.md)|データ ソースへの接続を確立します \(ODBC ドライバーを通じて\)|  
|[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)|データ ソースへの接続を確立します \(ODBC ドライバーを通じて\)|  
|[CDatabase::Rollback](../Topic/CDatabase::Rollback.md)|現在のトランザクション中に行われた逆の変更。  データ ソースが変更 **BeginTrans** の呼び出しで定義される前の状態にを返します。|  
|[CDatabase::SetLoginTimeout](../Topic/CDatabase::SetLoginTimeout.md)|秒数を設定します。その場合、データ ソースの接続の試みはタイムアウトします。|  
|[CDatabase::SetQueryTimeout](../Topic/CDatabase::SetQueryTimeout.md)|秒数を設定します。その場合、データベースのクエリ操作はタイムアウトします。  以降のレコードセット **\[開く\]**、`AddNew`、**\[編集\]**と **\[削除\]** の呼び出しに適用されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDatabase::m\_hdbc](../Topic/CDatabase::m_hdbc.md)|データ ソースの ODBC \(Open Database Connectivity\) 接続のハンドル。  型 **HDBC**。|  
  
## 解説  
 データ ソースは、データベース管理システム \(DBMS\) がホストするデータの特定のインスタンスです。  例では、Microsoft SQL Server、Microsoft Access、Borland の dBASE と xBASE が含まれます。  アプリケーションの `CDatabase` の一つ以上のオブジェクトをアクティブに一度に指定できます。  
  
> [!NOTE]
>  \(DAO\) ではなく、並べ替える Data Access Objects を使用すると、ODBC \(Open Database Connectivity\) クラスは、クラス [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) を代わりに使用します。  詳細については、" " [:概要 データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
 `CDatabase`を使用し、`CDatabase` オブジェクトを構築し、`OpenEx` のメンバー関数を呼び出します。  これは、接続を開きます。  次に、接続されたデータ ソースの操作の `CRecordset` のオブジェクトを構築するときに、`CDatabase` のオブジェクトに、レコードセットのコンストラクターにポインターを渡します。  接続を使い終わったら **\[閉じる\]** のメンバー関数を呼び出し、`CDatabase` オブジェクトを破棄します。  **\[閉じる\]** は、以前に閉じていないレコードセットを閉じます。  
  
 `CDatabase`に関する詳細については、" " [データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md) と [:概要 データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDatabase`  
  
## 必要条件  
 **Header:** afxdb.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)