---
title: "CDaoDatabase クラス | Microsoft Docs"
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
  - "CDaoDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabase クラス"
  - "CDaoDatabase クラス, およびワークスペース"
  - "CDaoDatabase クラス, vs. CDatabase クラス"
  - "CDatabase クラス, vs. CDaoDatabase クラス"
  - "データベース クラス [C++], DAO"
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoDatabase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

それを通じてデータを操作することのできるデータベースへの接続を表します。  
  
## 構文  
  
```  
class CDaoDatabase : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoDatabase::CDaoDatabase](../Topic/CDaoDatabase::CDaoDatabase.md)|`CDaoDatabase` オブジェクトを構築します。  オブジェクトをデータベースに接続するに **\[開く\]** を呼び出します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)|ゼロ以外のデータベース サポートのトランザクションを返します。|  
|[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)|`CDaoDatabase` のオブジェクトが更新可能である場合は、を返します \(読み取り専用\)。|  
|[CDaoDatabase::Close](../Topic/CDaoDatabase::Close.md)|データベース接続を閉じます。|  
|[CDaoDatabase::Create](../Topic/CDaoDatabase::Create.md)|基になる DAO のデータベース オブジェクトを作成し、`CDaoDatabase` のオブジェクトを初期化します。|  
|[CDaoDatabase::CreateRelation](../Topic/CDaoDatabase::CreateRelation.md)|新しいデータベースのテーブル間の関係を定義します。|  
|[CDaoDatabase::DeleteQueryDef](../Topic/CDaoDatabase::DeleteQueryDef.md)|データベースの QueryDefs のコレクションに保存される querydef オブジェクトを削除します。|  
|[CDaoDatabase::DeleteRelation](../Topic/CDaoDatabase::DeleteRelation.md)|データベースのテーブル間の既存の関係を削除します。|  
|[CDaoDatabase::DeleteTableDef](../Topic/CDaoDatabase::DeleteTableDef.md)|データベース テーブルの定義を削除します。  これは実際のテーブルとデータをすべて削除します。|  
|[CDaoDatabase::Execute](../Topic/CDaoDatabase::Execute.md)|アクション クエリを実行します。  結果は例外を返すクエリの **\[実行\]** を呼び出します。|  
|[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md)|データベースへの `CDaoDatabase` のオブジェクトを接続するために使用される接続文字列を返します。  ODBC に使用されます。|  
|[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)|現在使用中のデータベースの名前を返します。|  
|[CDaoDatabase::GetQueryDefCount](../Topic/CDaoDatabase::GetQueryDefCount.md)|データベースに対して定義されているクエリの数を返します。|  
|[CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)|データベースで定義された、指定されたクエリに関する情報を返します。|  
|[CDaoDatabase::GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)|秒数を返します。その場合、データベースのクエリ操作はタイムアウトします。  以降の影響を開いてに対して、**\[実行\]** の呼び出しなど、ODBC データ ソースの新規および更新および編集操作などの操作 \(のみ\) を追加します。|  
|[CDaoDatabase::GetRecordsAffected](../Topic/CDaoDatabase::GetRecordsAffected.md)|最後の更新、編集の影響を受けたレコードの数を返すか、呼び出しによって **\[実行\]**に操作またはを追加します。|  
|[CDaoDatabase::GetRelationCount](../Topic/CDaoDatabase::GetRelationCount.md)|データベースのテーブルの間で定義されている関係の数を返します。|  
|[CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)|データベースのテーブルの間で定義されている関係に関する情報を返します。|  
|[CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md)|データベースで定義されたテーブルの数を返します。|  
|[CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)|データベース テーブルの指定に関する情報を返します。|  
|[CDaoDatabase::GetVersion](../Topic/CDaoDatabase::GetVersion.md)|データベースに関連付けられたデータベース エンジンのバージョンを返します。|  
|[CDaoDatabase::IsOpen](../Topic/CDaoDatabase::IsOpen.md)|データベースへの `CDaoDatabase` のオブジェクトが現在接続された場合、を返します。|  
|[CDaoDatabase::Open](../Topic/CDaoDatabase::Open.md)|データベースへの接続を確立します。|  
|[CDaoDatabase::SetQueryTimeout](../Topic/CDaoDatabase::SetQueryTimeout.md)|秒数を設定します。その場合、データベースのクエリ操作は ODBC データ ソース \(のみ\) タイムアウトします。  以降の影響を開いてに対して、新しい更新、および削除の各操作を追加します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoDatabase::m\_pDAODatabase](../Topic/CDaoDatabase::m_pDAODatabase.md)|基になる DAO データベース オブジェクトへのポインター。|  
|[CDaoDatabase::m\_pWorkspace](../Topic/CDaoDatabase::m_pWorkspace.md)|データベースが含まれ、トランザクションの領域を定義する [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) オブジェクトへのポインター。|  
  
## 解説  
 サポートされているデータベース形式の詳細については、[GetName](../Topic/CDaoWorkspace::GetName.md) のメンバー関数に関するトピックを参照してください。  」、[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) のオブジェクトによって表される特定の「ワークスペースの `CDaoDatabase` の一つ以上のオブジェクトをアクティブに一度に指定できます。  ワークスペースと呼ばれる開いているデータベース オブジェクトのコレクション データベースのコレクションを保持します。  
  
> [!NOTE]
>  MFC DAO データベース クラスは、ODBC に基づいて MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  クラス `CDaoDatabase` は ODBC クラス [CDatabase](../../mfc/reference/cdatabase-class.md)に似たインターフェイスを提供します。  主な違いは `CDatabase` が ODBC \(Open Database Connectivity\) と、DBMS の ODBC ドライバーを通じて DBMS にアクセスすることです。  データ アクセスで`CDaoDatabase` のアクセスのデータは、Microsoft Jet データベース エンジンに基づいて \(DAO\) について説明します。  一般に、に基づく MFC DAO クラスは、ODBC \(DAO クラスより;できます。DAO ベースのクラスには独自のデータベース エンジンで ODBC ドライバーを通じて、含むデータにアクセスできます。  DAO ベースのクラスは、クラスによって DAO を直接呼び出さないでテーブルの追加など、データ定義言語の \(DDL\)、操作をサポートします。  
  
## 使用方法  
 レコードセット オブジェクトを作成するときにデータベース オブジェクトを暗黙的に作成できます。  ただし、データベース オブジェクトを明示的に作成できます。  `CDaoDatabase`と、既存のデータベースを明示的に使用するには、次のいずれかを実行する:  
  
-   [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) の開いているオブジェクトへのポインターを渡す `CDaoDatabase` のオブジェクトを構築します。  
  
-   またはワークスペースを指定せずに `CDaoDatabase` のオブジェクトを構築します \(MFC は一時的なワークスペース オブジェクトを作成します。  
  
 新しい Microsoft Jet \(.mdb\) データベースを作成し、`CDaoDatabase` オブジェクトを構築し、[&#91;作成&#93;](../Topic/CDaoDatabase::Create.md) のメンバー関数を呼び出します。  **\[作成\]**の後に **\[開く\]** を呼び出さないでください。  
  
 既存のデータベースを開き、`CDaoDatabase` オブジェクトを構築し、[&#91;開く&#93;](../Topic/CDaoDatabase::Open.md) のメンバー関数を呼び出します。  
  
 これらの方法のいずれかにワークスペースのコレクション データベースへの DAO データベース オブジェクトを追加し、データへの接続を開きます。  次に、接続されたデータベースの操作の [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)、または [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) のオブジェクトを構築するときに、`CDaoDatabase` のオブジェクトにオブジェクトのコンストラクターにポインターを渡します。  接続を使い終わったら [&#91;閉じる&#93;](../Topic/CDaoDatabase::Close.md) のメンバー関数を呼び出し、`CDaoDatabase` オブジェクトを破棄します。  **\[閉じる\]** は、以前に閉じていないレコードセットを閉じます。  
  
## トランザクション  
 データベースのトランザクション処理では、ワークスペースのレベルで指定されています。`CDaoWorkspace`クラスの [BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)、[CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)と [&#91;ロールバック&#93;](../Topic/CDaoWorkspace::Rollback.md) のメンバー関数を参照してください。  
  
## ODBC 接続  
 ODBC データ ソースを使用する方法は、Microsoft Jet \(.mdb\) データベースへの外部テーブルをアタッチできます。  
  
## コレクション  
 各データベースは、tabledef querydef、レコードセットと関係のオブジェクトの独自のコレクションを保持します。  クラス `CDaoDatabase` はこれらのオブジェクトを操作するためのメンバー関数を提供します。  
  
> [!NOTE]
>  オブジェクトは、DAO ではなく、MFC データベース オブジェクトに格納されます。  MFC は、tabledef、querydef とレコードセット オブジェクトの関係のないオブジェクトのクラスを提供します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoDatabase`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)