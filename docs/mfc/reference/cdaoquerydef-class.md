---
title: "CDaoQueryDef クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- QueryDef objects
- CDaoQueryDef class
- queries [Visual Studio], defining
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0bf06c68bb7072aa1907e4c730848cca9ff5e7d0
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef クラス
クエリ定義、つまり "querydef" を表し、通常はデータベースに保存されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|構築、 **CDaoQueryDef**オブジェクトです。 次を呼び出す**開く**または**作成**ニーズに応じて、します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|クエリ定義を保存されたクエリとして、データベースのクエリ定義のコレクションに追加します。|  
|[CDaoQueryDef::CanUpdate](#canupdate)|クエリは、データベースを更新できる場合は&0; 以外を返します。|  
|[CDaoQueryDef::Close](#close)|クエリ定義オブジェクトを閉じます。 これを終了するときに、C++ オブジェクトを破棄します。|  
|[CDaoQueryDef::Create](#create)|基になる DAO クエリ定義のオブジェクトを作成します。 クエリ定義を使用して、一時的なクエリまたは呼び出しとして**Append**をデータベースに保存します。|  
|[CDaoQueryDef::Execute](#execute)|クエリ定義オブジェクトによって定義されたクエリを実行します。|  
|[CDaoQueryDef::GetConnect](#getconnect)|クエリ定義に関連付けられている接続文字列を返します。 接続文字列では、データ ソースを識別します。 (SQL パススルー クエリ専用の場合、空の文字列です。)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|保存済みのクエリが作成された日付を返します。|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|保存済みのクエリが最後に更新された日付を返します。|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|クエリ定義で定義されたフィールドの数を返します。|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|指定したフィールドがクエリで定義されている情報を返します。|  
|[CDaoQueryDef::GetName](#getname)|クエリ定義の名前を返します。|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(ODBC クエリ) に対して、ODBC で使用されるタイムアウト値を返すクエリを実行するとします。 これは、クエリの操作が完了するためにどのくらいの期間判断されます。|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|クエリに定義されているパラメーターの数を返します。|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|クエリに指定されたパラメーターに関する情報を返します。|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|クエリに指定されたパラメーターの値を返します。|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|アクション クエリによって影響を受けたレコード数を返します。|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|クエリ定義で定義されているクエリ レコードを返す場合は&0; 以外を返します。|  
|[CDaoQueryDef::GetSQL](#getsql)|クエリ定義で定義されたクエリを指定する SQL 文字列を返します。|  
|[CDaoQueryDef::GetType](#gettype)|クエリの種類を取得します。 削除、更新、追加、テーブルの作成、および具合です。|  
|[CDaoQueryDef::IsOpen](#isopen)|クエリ定義が開いていて、実行できる場合は&0; 以外を返します。|  
|[CDaoQueryDef::Open](#open)|データベースのクエリ定義のコレクションに格納されている既存のクエリ定義を開きます。|  
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC データ ソースの SQL パススルー クエリの接続文字列を設定します。|  
|[CDaoQueryDef::SetName](#setname)|クエリ定義の作成時に使用中で名前を置き換えること、保存されたクエリの名前を設定します。|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|(ODBC クエリ) に対して、ODBC で使用されるタイムアウト値を設定、クエリが実行されるとします。|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|クエリに指定されたパラメーターの値を設定します。|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|クエリ定義がレコードを返すかどうかを指定します。 この属性を設定**TRUE** SQL パススルー クエリに対してのみ有効です。|  
|[CDaoQueryDef::SetSQL](#setsql)|クエリ定義で定義されたクエリを指定する SQL 文字列を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインター。|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|ポインター、`CDaoDatabase`クエリ定義が関連付けられているオブジェクト。 か、クエリ定義をデータベースに保存する可能性があります。|  
  
## <a name="remarks"></a>コメント  
 クエリ定義、クエリと、「作成日」と"ODBC Timeout"などのプロパティについて説明する SQL ステートメントを含むデータ アクセス オブジェクトは、します。 保存せずに、一時的なクエリ定義のオブジェクトを作成することもできますが、便利な — とはるかに効率的な-よくを保存するデータベースのクエリを再利用します。 A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトは、その保存したクエリ定義を含む QueryDefs コレクションと呼ばれる、コレクションを保持します。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含むデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="usage"></a>使用方法  
 クエリ定義やオブジェクトを使用するか保存済みのクエリを使用する新しいを作成するクエリまたは一時的なクエリを保存します。  
  
1.  常に、最初に構築、`CDaoQueryDef`へのポインターを提供するオブジェクト、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)クエリが属しているオブジェクトします。  
  
2.  目的に応じて、次の操作を行います。  
  
    -   保存済みのクエリを使用するには、クエリ定義オブジェクトを呼び出す[開く](#open)メンバー関数を保存したクエリの名前を指定します。  
  
    -   新しい保存されているクエリを作成するには、クエリ定義オブジェクトを呼び出す[作成](#create)メンバー関数の場合、クエリの名前を指定します。 まず[追加](#append)データベースのクエリ定義のコレクションに追加して、クエリを保存します。 **作成**クエリ定義では、開いている状態を呼び出した後は**作成**呼び出さないでください**開く**します。  
  
    -   一時的なクエリ定義を作成するには**作成**します。 クエリ名に空の文字列を渡します。 呼び出す必要はありません**Append**します。  
  
 クエリ定義オブジェクトの使用が終了したらを呼び出すその[閉じる](#close)メンバー関数は、クエリ定義オブジェクトを破棄します。  
  
> [!TIP]
>  保存されたクエリを作成する最も簡単な方法に作成して、Microsoft Access を使用して、データベースに保存します。 そして開きし、MFC コードで使用します。  
  
## <a name="purposes"></a>目的  
 次の目的のいずれかのクエリ定義オブジェクトを使用できます。  
  
-   作成する、`CDaoRecordset`オブジェクト  
  
-   オブジェクトの呼び出しに**Execute**を直接操作クエリ、または SQL パススルー クエリを実行するメンバー関数  
  
 任意の種類を選択、アクション、クロス集計、削除、更新プログラムを含めて、クエリのクエリ定義オブジェクトを使用して、追加、テーブルの作成、データ定義、SQL パススルー、共用体、および一括クエリできます。 クエリの種類は、指定した SQL ステートメントの内容によって決まります。 クエリの種類については、次を参照してください。、 **Execute**と[GetType](#gettype)メンバー関数。 レコード セットは行を返すでよく使われるクエリを通常使用する、**を選択しています.**キーワードです。 **実行**一括操作でよく使用されます。 詳細については、次を参照してください。 [Execute](#execute)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
## <a name="querydefs-and-recordsets"></a>クエリ定義とレコード セット  
 クエリ定義オブジェクトを使用して作成する、`CDaoRecordset`オブジェクトを通常、作成または前述のように、クエリ定義を開きます。 呼び出すときのクエリ定義オブジェクトにポインターを渡して、レコード セット オブジェクトを構築[cdaorecordset::open](../../mfc/reference/cdaorecordset-class.md#open)します。 渡すクエリ定義は、開いている状態にする必要があります。 詳細については、クラスを参照してください。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
 クエリ定義を使用すると、開いている状態である場合を除いて、レコード セット (クエリ定義の最も一般的な使用) を作成することはできません。 いずれかを呼び出して、クエリ定義を開いている状態に**開く**または**作成**します。  
  
## <a name="external-databases"></a>外部データベース  
 クエリ定義オブジェクトは、外部データベース エンジンのネイティブの SQL 構文を使用することをお勧めします。 たとえば、(Microsoft SQL Server で使用) とは、TRANSACT-SQL クエリを作成し、クエリ定義オブジェクトに格納します。 Microsoft Jet データベース エンジンに基づいていない SQL クエリを使用する必要がある場合は、外部データ ソースを指す接続文字列を指定する必要があります。 有効な接続文字列を含むクエリでは、データベース エンジンをバイパスし、外部データベース サーバーに直接処理するクエリを渡します。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは、それらを Microsoft Jet にアタッチする (。MDB) データベース。  
  
 関連情報については、「クエリ定義のオブジェクト」、「QueryDefs コレクション」および"CdbDatabase Object"DAO SDK のトピックを参照してください。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>CDaoQueryDef::Append  
 呼び出した後に、このメンバー関数を呼び出して[作成](#create)新しいクエリ オブジェクトを作成します。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 **追加**オブジェクトをデータベースのクエリ定義のコレクションに追加することにより、クエリ定義をデータベースに保存します。 一時オブジェクトとして追加することがなくクエリ定義を使用することができますが、これを保存する場合を呼び出す必要があります**Append**します。  
  
 一時的なクエリ定義オブジェクトを追加しようとすると、MFC は型の例外をスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
##  <a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 クエリ定義を変更できるかどうかを確認するには、このメンバー関数を呼び出すなどの名前または SQL 文字列の変更などです。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義を変更する権限を持っている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合は、クエリ定義を変更できます。  
  
-   読み取り専用に開かれているデータベースには基づいていません。  
  
-   データベースに対する更新アクセス許可があります。  
  
     これは、セキュリティ機能を実装しているかどうかによって異なります。 MFC ではセキュリティのサポートはされていません必要があります実装する自分で直接に DAO を呼び出すことによって、または Microsoft Access を使用しています。 DAO ヘルプの「アクセス許可プロパティ」トピックを参照してください。  
  
##  <a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 構築、 **CDaoQueryDef**オブジェクトです。  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 開いているへのポインター [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、データベースのクエリ定義のコレクション、コレクションに格納される新しいクエリまたは格納しないように、一時的なクエリに格納されている既存のクエリ定義を表すことができます。 次の手順は、クエリ定義の型によって異なります。  
  
-   オブジェクトは、既存のクエリ定義を表している場合、オブジェクトを呼び出す[開く](#open)メンバー関数を初期化します。  
  
-   オブジェクトは、保存する新しいクエリ定義を表している場合は、オブジェクトを呼び出す[作成](#create)メンバー関数。 これは、データベースのクエリ定義のコレクションにオブジェクトを追加します。 まず`CDaoQueryDef`メンバー関数、オブジェクトの属性を設定します。 最後に、呼び出す[Append](#append)します。  
  
-   オブジェクトは、一時的なクエリ (データベースに保存しない) の定義を表している場合は、呼び出す**作成**クエリの名前の空の文字列を渡すことです。 呼び出した後**作成**、直接その属性を設定して、クエリ定義を初期化します。 呼び出す必要はありません**Append**します。  
  
 クエリ定義の属性を設定するには、使用することができます、 [SetName](#setname)、 [SetSQL](#setsql)、 [SetConnect](#setconnect)、[に](#setodbctimeout)、および[SetReturnsRecords](#setreturnsrecords)メンバー関数。  
  
 クエリ定義オブジェクトを終了するときに呼び出す、[閉じる](#close)メンバー関数。 クエリ定義へのポインターがあればを使用して、**削除**C++ オブジェクトを破棄する演算子です。  
  
##  <a name="close"></a>CDaoQueryDef::Close  
 クエリ定義オブジェクトの使用が終了したときに、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 基になる DAO オブジェクトを解放が保存されている DAO クエリ定義オブジェクトまたは、C++ は破棄しませんのでクエリ定義を閉じる`CDaoQueryDef`オブジェクトです。 これは同じ[CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef)DAO (一時的なクエリ定義ではなければ)、データベースのクエリ定義のコレクションから、クエリ定義を削除します。  
  
##  <a name="create"></a>CDaoQueryDef::Create  
 このメンバー関数を呼び出して新しい保存されているクエリを作成する新しい一時的なクエリを作成します。  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 データベースに保存されたクエリの一意の名前。 詳細については、文字列、DAO ヘルプの「CreateQueryDef メソッド」を参照してください。 既定値、空の文字列を使用する場合は、一時的なクエリ定義が作成されます。 QueryDefs コレクションでは、このようなクエリは保存されません。  
  
 `lpszSQL`  
 クエリを定義する SQL 文字列。 既定値を受け入れる場合**NULL**、後で呼び出す必要があります[SetSQL](#setsql)文字列を設定します。 それまでは、クエリは、定義されていません。 ただしを開くには、レコード セット未定義のクエリを使用することができます。詳細については、「解説」を参照してください。 QueryDefs コレクションをクエリ定義を追加する前に、SQL ステートメントを定義する必要があります。  
  
### <a name="remarks"></a>コメント  
 内の名前を渡す場合`lpszName`を呼び出せます[Append](#append)データベースのクエリ定義のコレクションにクエリ定義を保存します。 それ以外の場合、オブジェクトは一時的なクエリ定義であり、保存されません。 いずれの場合、クエリ定義は、開いている状態では、作成に使用できる、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトまたはクエリ定義の[Execute](#execute)メンバー関数。  
  
 内の SQL ステートメントを指定しない場合`lpszSQL`を使用してクエリを実行することはできません**Execute**が、レコード セットの作成に使用することができます。 その場合は、MFC は、レコード セットの既定の SQL ステートメントを使用します。  
  
##  <a name="execute"></a>CDaoQueryDef::Execute  
 クエリ定義オブジェクトによって定義されたクエリを実行するには、このメンバー関数を呼び出します。  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOptions`  
 クエリの特性を決定する整数。 関連情報については、DAO ヘルプの「メソッドの実行」を参照してください。 ビットごとの OR 演算子を使用することができます ( **|**) をこの引数には、次の定数を組み合わせます。  
  
- **dbDenyWrite**他のユーザーへの書き込み権限を拒否します。  
  
- **組み合わせて**一貫性のない更新プログラムです。  
  
- **指定できます**一貫性のある更新します。  
  
- **dbSQLPassThrough** SQL パススルーします。 原因で処理するために ODBC データベースに渡される SQL ステートメント。  
  
- **dbFailOnError**既定値です。 エラーが発生した場合に、更新およびロールバック レポート エラーをユーザーにします。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合は、実行時エラーを生成します。  
  
> [!NOTE]
>  用語の説明「整合性がありません」と「一貫性」DAO ヘルプの「メソッドの実行」トピックを参照してください。  
  
### <a name="remarks"></a>コメント  
 この方法で実行するために使用されるクエリ定義オブジェクトを次のクエリの種類のいずれかのみ表現できます。  
  
-   アクションのクエリ  
  
-   SQL パススルー クエリ  
  
 **実行**select クエリなどのレコードを返すクエリでは機能しません。 **実行**など使用一括操作のクエリの一般的**更新**、**挿入**、または**SELECT INTO**、またはデータ定義言語 (DDL) 操作です。  
  
> [!TIP]
>  ODBC データ ソースを使用することをお勧めは、Microsoft Jet にテーブルをアタッチする (。MDB) データベース。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
 呼び出す、 [GetRecordsAffected](#getrecordsaffected)最新によって影響を受けたレコードの数を特定するクエリ定義オブジェクトのメンバー関数**Execute**呼び出します。 たとえば、`GetRecordsAffected`削除、更新、またはアクション クエリを実行するときに挿入されるレコードの数に関する情報を返します。 返されるカウントを重ねて表示を更新または削除時に関連付けられたテーブル内の変更が反映反映されません。  
  
 両方を含めた場合**組み合わせて**と**指定できます**またはどちらもを含める場合、結果が、既定では、**組み合わせて**します。  
  
 **実行**はレコード セットを返しません。 使用して**Execute**レコードを選択するクエリに MFC 型の例外をスローすると、 [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
##  <a name="getconnect"></a>CDaoQueryDef::GetConnect  
 このメンバー関数を呼び出して、クエリ定義のデータ ソースに関連付けられている接続文字列を取得します。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)クエリ定義の接続文字列を含みます。  
  
### <a name="remarks"></a>コメント  
 この関数は、ODBC データ ソースと特定の ISAM ドライバーでのみ使用されます。 Microsoft Jet では使用されません (します。MDB) データベース。この場合、`GetConnect`空の文字列を返します。 詳細については、次を参照してください。 [SetConnect](#setconnect)します。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは接続先をします。MDB データベースです。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
 接続文字列については、DAO のヘルプ「プロパティの接続」を参照してください。  
  
##  <a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 クエリ定義オブジェクトが作成された日付を取得するには、このメンバー関数を呼び出します。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 A[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)クエリ定義が作成された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 最後に更新された日付にクエリ定義オブジェクトを取得するには、このメンバー関数の呼び出し: とそのプロパティのいずれかが変更された、名、SQL 文字列、その接続文字列などです。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 A[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)クエリ定義が最後に更新された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 クエリのフィールドの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 クエリで定義されているフィールドの数。  
  
### <a name="remarks"></a>コメント  
 `GetFieldCount`クエリ定義のすべてのフィールドをループ処理に便利です。 そのためを使用して`GetFieldCount`と共に[GetFieldInfo](#getfieldinfo)します。  
  
##  <a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo  
 さまざまな種類のクエリ定義で定義されているフィールドに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、クエリ定義のフィールド コレクションの該当フィールドの&0; から始まるインデックス。  
  
 `fieldinfo`  
 参照、`CDaoFieldInfo`オブジェクトを必要な情報を返します。  
  
 `dwInfoOptions`  
 取得するフィールドに関する情報を指定するオプションです。 使用可能なオプションは、それらの原因として何を返す関数もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、種類、サイズ、属性  
  
- `AFX_DAO_SECONDARY_INFO`プライマリ情報に加えて: 必要な序数の位置、長さ&0; を許可する、ソース フィールド、外部名、ソース テーブル、照合順序  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報に加えて: 既定値、エラー メッセージの検証規則  
  
 `lpszName`  
 名前で検索する場合、該当するフィールドの名前を表す文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`fieldinfo`を参照してください、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体は、わかりやすい情報に対応するメンバー`dwInfoOptions`上です。 1 つのレベルの情報を要求すると、その情報も同様のレベルを取得できます。  
  
##  <a name="getname"></a>CDaoQueryDef::GetName  
 このメンバー関数を呼び出して、クエリ定義で表されるクエリの名前を取得します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ名を返します。  
  
### <a name="remarks"></a>コメント  
 クエリ定義名は一意のユーザー定義の名前です。 クエリ定義名の詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 ODBC データ ソースへのクエリがタイムアウトになる前に、現在の制限時間を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 クエリするまでの秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>コメント  
 この制限時間については、DAO ヘルプの「補足プロパティ」を参照してください。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは、それらを Microsoft Jet にアタッチする (。MDB) データベース。 詳細については、"にアクセスする外部のデータベースと DAO"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 保存されたクエリのパラメーターの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>戻り値  
 クエリで定義されているパラメーターの数。  
  
### <a name="remarks"></a>コメント  
 `GetParameterCount`クエリ定義のすべてのパラメーターをループ処理に便利です。 そのためを使用して`GetParameterCount`と共に[GetParameterInfo](#getparameterinfo)します。  
  
 関連情報については、「パラメーター オブジェクト」、「パラメーターのコレクション」および"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo  
 このメンバー関数を呼び出してクエリ定義で定義されているパラメーターに関する情報を取得します。  
  
```  
void GetParameterInfo(
    int nIndex,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetParameterInfo(
    LPCTSTR lpszName,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、クエリ定義のパラメーター コレクションで目的のパラメーターの&0; から始まるインデックス。  
  
 `paraminfo`  
 参照、 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)必要な情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得するパラメーターに関する情報を指定するオプションです。 使用可能なオプションはと共にを返す関数がそのとおりです。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、型  
  
 `lpszName`  
 名前で検索する場合、必要なパラメーターの名前を表す文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`paraminfo`を参照してください、 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md)構造体。 この構造体は、わかりやすい情報に対応するメンバー`dwInfoOptions`上です。  
  
 関連情報については、"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getparamvalue"></a>CDaoQueryDef::GetParamValue  
 クエリ定義のパラメーター コレクションに格納されている指定されたパラメーターの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 パラメーター値を取得する、名前で検索する場合の名前。  
  
 `nIndex`  
 インデックスで検索する場合のクエリ定義のパラメーター コレクション内のパラメーターの&0; から始まるインデックス。 呼び出すには、この値を取得できます[GetParameterCount](#getparametercount)と[GetParameterInfo](#getparameterinfo)します。  
  
### <a name="return-value"></a>戻り値  
 クラスのオブジェクト[COleVariant](../../mfc/reference/colevariant-class.md)パラメーターの値を格納します。  
  
### <a name="remarks"></a>コメント  
 パラメーターは、名、またはコレクション内の順序位置でアクセスできます。  
  
 関連情報については、"パラメーターの宣言 (SQL)"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 最後の呼び出しの影響を受けたレコードの数を判断するには、このメンバー関数を呼び出す[Execute](#execute)します。  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>戻り値  
 影響を受けたレコードの数。  
  
### <a name="remarks"></a>コメント  
 返されるカウントを重ねて表示を更新または削除時に関連付けられたテーブル内の変更が反映反映されません。  
  
 関連情報については、"RecordsAffected Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 クエリ定義をレコードを返すクエリに基づいているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>戻り値  
 レコードを返すクエリ定義は、クエリに基づいている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、SQL パススルー クエリのみ使用されます。 SQL クエリの詳細については、次を参照してください。、 [Execute](#execute)メンバー関数。 SQL パススルー クエリを使用した作業の詳細については、次を参照してください。、 [SetReturnsRecords](#setreturnsrecords)メンバー関数。  
  
 関連情報については、DAO のヘルプで「レコード表示プロパティ」を参照してください。  
  
##  <a name="getsql"></a>CDaoQueryDef::GetSQL  
 クエリ定義の基になるクエリを定義する SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義の基になるクエリを定義する SQL ステートメント。  
  
### <a name="remarks"></a>コメント  
 キーワードやテーブル名の文字列をおそらく解析されます。  
  
 関連情報については、"SQL Property"、"比較の Microsoft Jet データベース エンジン SQL と ANSI SQL"、および「クエリを実行する、データベースと SQL でコード」DAO ヘルプのトピックを参照してください。  
  
##  <a name="gettype"></a>CDaoQueryDef::GetType  
 このメンバー関数を呼び出してクエリ定義のクエリの種類を決定します。  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>戻り値  
 クエリ定義で定義されたクエリの型。 値は、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 どのような文字列に指定したクエリ定義の SQL クエリを作成するか、既存のクエリ定義の場合で、クエリの種類が設定されて[SetSQL](#setsql)メンバー関数。 この関数によって返されるクエリの種類には、次の値のいずれかを指定できます。  
  
- **dbQSelect**選択  
  
- **dbQAction**アクション  
  
- **dbQCrosstab**クロス集計  
  
- **dbQDelete**の削除  
  
- **dbQUpdate**更新  
  
- **dbQAppend**追加  
  
- **dbQMakeTable**テーブルの作成  
  
- **dbQDDL**データ定義  
  
- **dbQSQLPassThrough**パススルー  
  
- **dbQSetOperation**共用体  
  
- **dbQSPTBulk**併用**dbQSQLPassThrough**レコードを返さないクエリを指定します。  
  
> [!NOTE]
>  SQL パススルー クエリを作成するに設定しないで、 **dbSQLPassThrough**定数です。 これは自動的に設定 Microsoft Jet データベース エンジンによってクエリ定義オブジェクトを作成し、接続文字列を設定します。  
  
 SQL 文字列については、次を参照してください。 [GetSQL](#getsql)します。 クエリの種類については、次を参照してください。 [Execute](#execute)します。  
  
##  <a name="isopen"></a>CDaoQueryDef::IsOpen  
 判断するには、このメンバー関数を呼び出すかどうか、`CDaoQueryDef`オブジェクトが現在開いています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDaoQueryDef`オブジェクトが現在開いている。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 クエリ定義は、の呼び出しに使用する前に、開いている状態である必要があります[Execute](#execute)を作成したり、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトです。 か、開いている状態の呼び出しにクエリ定義を配置する[作成](#create)(の新しいクエリ定義の場合) または[を開く](#open)(既存のクエリ定義) のです。  
  
##  <a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 ポインターを含む、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)クエリ定義オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 データベースに直接アクセスする必要がある場合は、このポインターを使用して、データベースのコレクションでオブジェクトへの他のクエリ定義またはレコード セットへのポインターの取得などです。  
  
##  <a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 基になる DAO クエリ定義オブジェクトの OLE インターフェイスへのポインターが含まれています。  
  
### <a name="remarks"></a>コメント  
 このポインターは、完全性と他のクラスと一貫性のために提供されます。 ただし、MFC には、DAO のクエリ定義ではなく完全にカプセル化するためいないが必要になる可能性があります。 それを使用する場合は注意: の実行内容がわかっていない限り、ポインターの値を変更して具体的には、です。  
  
##  <a name="open"></a>CDaoQueryDef::Open  
 データベースのクエリ定義のコレクションに以前に保存したクエリ定義を開くには、このメンバー関数を呼び出します。  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 開くには保存したクエリ定義の名前を表す文字列。 使用することができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 クエリ定義が開いたらを呼び出すことができます、 [Execute](#execute)メンバー関数、または作成するクエリ定義を使用して、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトです。  
  
##  <a name="setconnect"></a>CDaoQueryDef::SetConnect  
 クエリ定義オブジェクトの接続文字列を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszConnect`  
 関連付けられた接続文字列を含む文字列[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 接続文字列を使用して、ODBC や必要に応じて、特定の ISAM ドライバーへの追加情報を渡します。 Microsoft Jet 用は使用されません (します。MDB) データベース。  
  
> [!TIP]
>  ODBC テーブルを使用することをお勧めは接続先をします。MDB データベースです。  
  
 ODBC データ ソースに SQL パススルー クエリを表すクエリを実行する前に設定された接続文字列で`SetConnect`を呼び出すと[SetReturnsRecords](#setreturnsrecords)クエリがレコードを返すかどうかを指定します。  
  
 詳細については、接続文字列の構造と接続文字列コンポーネントの例については、DAO のヘルプ「プロパティの接続」を参照してください。  
  
##  <a name="setname"></a>CDaoQueryDef::SetName  
 ない一時的なクエリ定義の名前を変更する場合は、このメンバー関数を呼び出します。  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 関連付けられた nontemporary クエリの新しい名前を表す文字列[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 クエリ定義名は、ユーザー定義の一意の名前です。 呼び出すことができます`SetName`クエリ定義の前に、オブジェクトがクエリ定義のコレクションに追加されます。  
  
##  <a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 ODBC データ ソースへのクエリがタイムアウトになる前に、制限時間を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 *nODBCTimeout*  
 クエリするまでの秒数がタイムアウトになりました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数では、「タイムアウト」接続されているデータ ソースに対する後続の処理までの秒数の既定をオーバーライドできます。 操作は、ネットワーク アクセスの問題、過剰なクエリの処理時間によるタイムアウト可能性があります。 呼び出す`SetODBCTimeout`クエリ タイムアウト値を変更する場合は、このクエリでクエリを実行する前にします。 (ODBC 接続を再利用とタイムアウト値は、同じ接続上のすべてのクライアントで同じです。)  
  
 クエリ タイムアウトの既定値は、60 秒です。  
  
##  <a name="setparamvalue"></a>CDaoQueryDef::SetParamValue  
 実行時にクエリ定義でパラメーターの値を設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 パラメーターを設定する値の名前。  
  
 `varValue`  
 値が設定されます。「解説」を参照してください。  
  
 `nIndex`  
 クエリ定義のパラメーター コレクション内のパラメーターの序数位置。 呼び出すには、この値を取得できます[GetParameterCount](#getparametercount)と[GetParameterInfo](#getparameterinfo)します。  
  
### <a name="remarks"></a>コメント  
 パラメーター既に、クエリ定義の SQL 文字列の一部として設定されていなければなりません。 パラメーターは、名、またはコレクション内の順序位置でアクセスできます。  
  
 として設定する値を指定して、`COleVariant`オブジェクトです。 目的の値と型の設定については、`COleVariant`オブジェクト、クラスを参照して[COleVariant](../../mfc/reference/colevariant-class.md)します。  
  
##  <a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 外部データベースに SQL パススルー クエリの設定プロセスの一環として、この関数を呼び出します。  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>パラメーター  
 *bReturnsRecords*  
 渡す**TRUE** 、外部データベースにクエリがレコードを返す場合は、それ以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このような場合には、クエリ定義を作成し、使用して他のプロパティを設定する必要があります、`CDaoQueryDef`メンバー関数。 外部データベースについては、次を参照してください。 [SetConnect](#setconnect)します。  
  
##  <a name="setsql"></a>CDaoQueryDef::SetSQL  
 このメンバー関数を呼び出してクエリを実行する SQL ステートメントを設定します。  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSQL`  
 実行に適した完全な SQL ステートメントを含む文字列。 この文字列の構文は、DBMS に依存する、クエリのターゲットです。 Microsoft Jet データベース エンジンで使用される構文の詳細については、「作成 SQL ステートメントでコード」DAO ヘルプのトピックを参照してください。  
  
### <a name="remarks"></a>コメント  
 一般的な使用`SetSQL`SQL パススルー クエリで使用するためのクエリ定義オブジェクトを設定します。 (対象となる DBMS 上の SQL パススルー クエリの構文、DBMS のマニュアルを参照してください)。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)

