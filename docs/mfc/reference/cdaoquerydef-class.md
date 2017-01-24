---
title: "CDaoQueryDef クラス | Microsoft Docs"
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
  - "CDaoQueryDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDef クラス"
  - "クエリ [Visual Studio], 定義"
  - "QueryDef オブジェクト"
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoQueryDef クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クエリ定義、つまり "querydef" を表し、通常はデータベースに保存されています。  
  
## 構文  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoQueryDef::CDaoQueryDef](../Topic/CDaoQueryDef::CDaoQueryDef.md)|**CDaoQueryDef** オブジェクトを構築します。  必要に応じて、次の呼び出し **\[開く\]** か、**\[作成\]**。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoQueryDef::Append](../Topic/CDaoQueryDef::Append.md)|データベースの QueryDefs のコレクションに、querydef ように保存されたクエリを追加します。|  
|[CDaoQueryDef::CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)|クエリがデータベースを更新できる場合はを返します。|  
|[CDaoQueryDef::Close](../Topic/CDaoQueryDef::Close.md)|querydef オブジェクトを閉じます。  これを終了するときに C\+\+ オブジェクトを破棄します。|  
|[CDaoQueryDef::Create](../Topic/CDaoQueryDef::Create.md)|基になる DAO の querydef オブジェクトを作成します。  データベースに保存するには、一時的なクエリ、または呼び出し **\[追加\]** として、querydef を使用します。|  
|[CDaoQueryDef::Execute](../Topic/CDaoQueryDef::Execute.md)|querydef オブジェクトによって定義されるクエリを実行します。|  
|[CDaoQueryDef::GetConnect](../Topic/CDaoQueryDef::GetConnect.md)|querydef に関連付けられている接続文字列を返します。  接続文字列は、データ ソースを識別します。  \(SQL のパススルー クエリの場合のみ; それ以外の場合は空の文字列。\)|  
|[CDaoQueryDef::GetDateCreated](../Topic/CDaoQueryDef::GetDateCreated.md)|保存されたクエリが作成された日付を返します。|  
|[CDaoQueryDef::GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)|保存されたクエリの最終更新日を返します。|  
|[CDaoQueryDef::GetFieldCount](../Topic/CDaoQueryDef::GetFieldCount.md)|querydef して定義されたフィールドの数を返します。|  
|[CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)|クエリで定義される指定したフィールドに関する情報を返します。|  
|[CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md)|querydef の名前を返します。|  
|[CDaoQueryDef::GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)|querydef が実行されると、ODBC によって使用されるタイムアウト値を返します \(ODBC のクエリの場合\)。  これはクエリの処理を完了するためにどの程度を判定します。|  
|[CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)|クエリに対して定義されているパラメーターの数を返します。|  
|[CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)|クエリに指定されたパラメーターに関する情報を返します。|  
|[CDaoQueryDef::GetParamValue](../Topic/CDaoQueryDef::GetParamValue.md)|クエリに指定されたパラメーターの値を返します。|  
|[CDaoQueryDef::GetRecordsAffected](../Topic/CDaoQueryDef::GetRecordsAffected.md)|アクション クエリによって影響を受けたレコードの数を返します。|  
|[CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md)|querydef で定義されるクエリがレコードを返す場合は、を返します。|  
|[CDaoQueryDef::GetSQL](../Topic/CDaoQueryDef::GetSQL.md)|querydef で定義されるクエリを指定する SQL 文字列を返します。|  
|[CDaoQueryDef::GetType](../Topic/CDaoQueryDef::GetType.md)|クエリの型が返されます: テーブルなど、作削除して、更新して追加します。|  
|[CDaoQueryDef::IsOpen](../Topic/CDaoQueryDef::IsOpen.md)|querydef を開いてで実装できる場合は、を返します。|  
|[CDaoQueryDef::Open](../Topic/CDaoQueryDef::Open.md)|データベースの QueryDefs のコレクションに格納されている既存の querydef を開きます。|  
|[CDaoQueryDef::SetConnect](../Topic/CDaoQueryDef::SetConnect.md)|ODBC データ ソースの SQL のパススルー クエリの接続文字列を設定します。|  
|[CDaoQueryDef::SetName](../Topic/CDaoQueryDef::SetName.md)|querydef の作成時に使用されている名前を置換保存されたクエリの名前を設定します。|  
|[CDaoQueryDef::SetODBCTimeout](../Topic/CDaoQueryDef::SetODBCTimeout.md)|querydef が実行されたときにタイムアウト値を ODBC によって使用される設定 \(ODBC のクエリの場合\)。|  
|[CDaoQueryDef::SetParamValue](../Topic/CDaoQueryDef::SetParamValue.md)|クエリに指定されたパラメーターの値を設定します。|  
|[CDaoQueryDef::SetReturnsRecords](../Topic/CDaoQueryDef::SetReturnsRecords.md)|querydef がレコードを返すかどうかを指定します。  **\[真\]** にこの属性を設定すると、SQL のパススルー クエリに対してのみ有効です。|  
|[CDaoQueryDef::SetSQL](../Topic/CDaoQueryDef::SetSQL.md)|querydef で定義されるクエリを指定する SQL 文字列を設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoQueryDef::m\_pDAOQueryDef](../Topic/CDaoQueryDef::m_pDAOQueryDef.md)|基になる DAO の querydef オブジェクトの OLE インターフェイスへのポインター。|  
|[CDaoQueryDef::m\_pDatabase](../Topic/CDaoQueryDef::m_pDatabase.md)|querydef が関連付けられている `CDaoDatabase` オブジェクトへのポインター。  querydef はデータベースに保存またはない可能性があります。|  
  
## 解説  
 querydef は、クエリの説明、および「作成され」、ODBC タイムアウト日付などのプロパティを」、含む SQL ステートメントのデータ アクセス オブジェクトです。また、変更を保存せずに一時的な querydef オブジェクトを作成しているデータベースの一般に再利用されたクエリを保存すると、—、効率—便利です。  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) のオブジェクトが保存された querydefs を含む、コレクション QueryDefs のコレクションを保持します。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます。  一般に、に基づく MFC DAO クラスは、ODBC \(DAO クラスより;できます。DAO ベースのクラスには独自のデータベース エンジンで ODBC ドライバーを通じて、含むデータにアクセスできます。  DAO ベースのクラスは、クラスによって DAO を直接呼び出さないでテーブルの追加など、データ定義言語の \(DDL\)、操作をサポートします。  
  
## 使用方法  
 保存されたクエリを使用するには、querydef オブジェクトまたは新しい保存されたクエリまたは一時的なクエリを作成するには:  
  
1.  いずれの場合も、最初にクエリが属する [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) オブジェクトへのポインターを指定する `CDaoQueryDef` のオブジェクトを構築します。  
  
2.  を与えない場合によっては、次する:  
  
    -   既存のを使用すると、クエリを呼び出します。保存されたクエリの名前を指定して、querydef オブジェクトの [&#91;開く&#93;](../Topic/CDaoQueryDef::Open.md) のメンバー関数をしました。  
  
    -   新しい保存されたクエリを作成するには、クエリの名前を指定して、querydef オブジェクトの [&#91;作成&#93;](../Topic/CDaoQueryDef::Create.md) のメンバー関数を呼び出します。  次に、データベースの QueryDefs のコレクションにテンプレートを追加してクエリを保存するに [&#91;追加&#93;](../Topic/CDaoQueryDef::Append.md) を呼び出します。  **\[作成\]** は、開いている状態で、querydef を入力するため、**\[作成\]** を呼び出した後 **\[開く\]**を呼び出さないでください。  
  
    -   一時 querydef を作成するには、**\[作成\]**を呼び出します。  クエリの名前の空の文字列を渡します。  **\[追加\]**を呼び出さないでください。  
  
 querydef オブジェクトを使い終わったら [&#91;閉じる&#93;](../Topic/CDaoQueryDef::Close.md) のメンバー関数を呼び出します。; その後、querydef オブジェクトを破棄します。  
  
> [!TIP]
>  保存されたクエリを作成する最も簡単な方法は、を作成し、Microsoft Access を使用して、データベースに格納します。  次に、MFC コードでそれらを開いて使用できます。  
  
## 目的  
 次の目的に対しても、querydef オブジェクトを使用する:  
  
-   `CDaoRecordset` のオブジェクトを作成するには  
  
-   オブジェクトの **\[実行\]** のメンバー関数を直接操作または SQL クエリのパススルー クエリを実行するために呼び出すには  
  
 を含むクエリの任意の型のデータ定義、SQL のパススルー、共用体、サイズのクエリ querydef オブジェクトを選択し、アクション、crosstab、削除、更新、作使用し、テーブル、追加できます。  クエリの型が、指定した SQL ステートメントの内容によって決まります。  クエリの型については、**\[実行\]** と [Object](../Topic/CDaoQueryDef::GetType.md) のメンバー関数を参照してください。  レコードセットは、行を返すクエリ、通常、SELECT… **を使用してそれらのは一般的ですキーワードで**。  **\[実行\]** は一括操作に最も一般的です。  詳細については、[&#91;実行&#93;](../Topic/CDaoQueryDef::Execute.md) と [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)を参照してください。  
  
## レコードセットと Querydefs  
 `CDaoRecordset` のオブジェクトを作成するために、querydef オブジェクトを使用するには、通常、querydef を作成するか、上のように表示されます。  次 [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)を呼び出すときに、querydef オブジェクトへのポインターを渡すレコードセット オブジェクトを構築します。  に渡す querydef は、開いている状態である必要があります。  詳細については、クラス [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)を参照してください。  
  
 開いている状態にあるレコードセット \(querydef の一般的な使用\) を作成するには、querydef を使用できません。  **\[開く\]** か **\[作成\]**を呼び出して、開いている状態で、querydef を入力します。  
  
## 外部データベース  
 Querydef のオブジェクトは、外部データベース エンジンのネイティブの SQL 言語を使用する場合に適しています。  \(Microsoft SQL Server で使用される\) たとえば、処理の SQL クエリを作成し、querydef オブジェクトに格納することができます。  Microsoft Jet データベース エンジンに基づいて SQL クエリを使用する必要がある場合は、外部データ ソースを指す接続文字列を指定する必要があります。  有効な接続文字列とのクエリはデータベース エンジンを使用しないで、処理の外部データベース サーバーに直接クエリを渡します。  
  
> [!TIP]
>  ODBC のテーブルを使用する場合に推奨される方法は、Microsoft Jet \(.mdb\) データベースにユーザーをアタッチできます。  
  
 関連情報については、DAO SDK の「QueryDef オブジェクトのコレクション QueryDefs」、「」、および「CdbDatabase オブジェクト」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoQueryDef`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)