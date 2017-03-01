---
title: "CDatabase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDatabase
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- MFC [C++], ODBC
- ODBC [C++], CDatabase class
- ODBC database class
- database connections [C++], CDatabase class
- CDatabase class
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
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
ms.openlocfilehash: a14025d712f09bef2b6b749d46cac1b1371fd4e3
ms.lasthandoff: 02/24/2017

---
# <a name="cdatabase-class"></a>CDatabase クラス
データ ソースへの接続を表します。これを通じてデータ ソース上で操作を行うことができます。  
  
## <a name="syntax"></a>構文  
  
```  
class CDatabase : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::CDatabase](#cdatabase)|`CDatabase` オブジェクトを構築します。 呼び出してオブジェクトを初期化する必要があります`OpenEx`または**開く**します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|Â €「トランザクション」を開始"一連の呼び出し元に戻せる状態、 `AddNew`、**編集**、**削除**と**更新**クラスのメンバー関数`CRecordset`â €"接続されているデータ ソースにします。 データ ソースのトランザクションをサポートする必要があります**BeginTrans**を有効します。|  
|[CDatabase::BindParameters](#bindparameters)|呼び出しの前にパラメーターをバインドすることができます`CDatabase::ExecuteSQL`します。|  
|[CDatabase::Cancel](#cancel)|非同期操作または&2; 番目のスレッドからのプロセスをキャンセルします。|  
|[CDatabase::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は&0; 以外を返します。|  
|[CDatabase::CanUpdate](#canupdate)|場合は&0; 以外の値を返し、`CDatabase`オブジェクトが更新可能な (いない読み取り専用)。|  
|[CDatabase::Close](#close)|データ ソース接続を閉じます。|  
|[CDatabase::CommitTrans](#committrans)|によって開始されたトランザクションが完了すると**BeginTrans**します。 データ ソースを変更するトランザクションにコマンドが実行されます。|  
|[CDatabase::ExecuteSQL](#executesql)|SQL ステートメントを実行します。 データ レコードが返されません。|  
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|レコード セット オブジェクトに使用されるブックマークが保持されている操作を識別します。|  
|[Cdatabase::getconnect](#getconnect)|接続に使用する ODBC 接続文字列を返す、`CDatabase`オブジェクトをデータ ソースにします。|  
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|開いているレコード セット オブジェクトでトランザクションをコミットする効果を識別します。|  
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|開いているレコード セット オブジェクトでトランザクションのロールバックの効果を識別します。|  
|[CDatabase::GetDatabaseName](#getdatabasename)|現在使用中のデータベースの名前を返します。|  
|[CDatabase::IsOpen](#isopen)|場合は&0; 以外の値を返し、`CDatabase`オブジェクトがデータ ソースに現在接続されています。|  
|[CDatabase::OnSetOptions](#onsetoptions)|標準的な接続オプションを設定するためにフレームワークによって呼び出されます。 既定の実装では、クエリのタイムアウト値を設定します。 前もってこれらのオプションを作成するには、呼び出す`SetQueryTimeout`します。|  
|[Cdatabase::open](#open)|(の ODBC ドライバーを通じて) データ ソースへの接続を確立します。|  
|[Cdatabase::openex](#openex)|(の ODBC ドライバーを通じて) データ ソースへの接続を確立します。|  
|[CDatabase::Rollback](#rollback)|現在のトランザクションで加えられた変更を反転させます。 定義されている前の状態にデータ ソースを返します、 **BeginTrans**呼び出し、変更せずにします。|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|データ ソース接続の試行はタイムアウトするまでします秒数を設定します。|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|データベースの後の秒数のクエリ操作のセットは、タイムアウトします。 後続のすべてのレコード セットの影響を与える**開く**、 `AddNew`、**編集**と**削除**呼び出しです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDatabase::m_hdbc](#m_hdbc)|データ ソースへの open Database Connectivity (ODBC) 接続ハンドルです。 型**HDBC**します。|  
  
## <a name="remarks"></a>コメント  
 データ ソースは、いくつかのデータベース管理システム (DBMS) によってホストされているデータの特定のインスタンスです。 例としては、Microsoft SQL Server、Microsoft Access、Borland dBASE xBASE です。 1 つまたは複数を持てる`CDatabase`時、アプリケーションでアクティブなオブジェクトです。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)代わりにします。 詳細については、記事を参照してください。[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
 使用する`CDatabase`、構築、`CDatabase`オブジェクトと呼び出しの`OpenEx`メンバー関数。 これは、接続を開きます。 構築するときに`CRecordset`接続されているデータ ソースで動作しているオブジェクトは、レコード セット コンス トラクターへのポインターを渡す、`CDatabase`オブジェクトです。 接続を使用してが完了したらを呼び出す、**閉じる**メンバー関数し、破棄、`CDatabase`オブジェクトです。 **閉じる**閉じられていないすべてのレコード セットを閉じます。  
  
 詳細については`CDatabase`、記事を参照して[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)と[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="a-namebegintransa--cdatabasebegintrans"></a><a name="begintrans"></a>CDatabase::BeginTrans  
 このメンバー関数を呼び出して、接続されているデータ ソースでトランザクションを開始します。  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功し、変更がのみで手動でコミットされた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 トランザクションでは、1 つまたは複数の呼び出しの`AddNew`、**編集**、**削除**、および**更新**のメンバー関数、`CRecordset`オブジェクトです。 トランザクションを開始する前に、`CDatabase`オブジェクト必要があります既にが接続されたデータ ソースに呼び出すことによって、`OpenEx`または**開く**メンバー関数。 トランザクションの最後で呼び出す[CommitTrans](#committrans)受け入れをデータ ソースに対するすべての変更 (実行して) を呼び出したり[ロールバック](#rollback)全体のトランザクションを中止します。 呼び出す**BeginTrans**後、トランザクションに関連するすべてのレコード セットを開くし、として、実際の更新操作。  
  
> [!CAUTION]
>  ODBC ドライバーによっては、呼び出す前にレコード セットを開いて**BeginTrans**を呼び出すときに問題が発生する可能性があります**ロールバック**します。 使用している特定のドライバーを確認する必要があります。 たとえば、Microsoft ODBC デスクトップ ドライバー パック 3.0 に含まれる Microsoft Access ドライバーを使用する場合に、開いているカーソルを持つ任意のデータベースでトランザクションを開始する必要がありますいない Jet データベース エンジンの要件を考慮する必要があります。 MFC データベース クラスで開いているカーソルは開いていることを意味`CRecordset`オブジェクトです。 詳細については、次を参照してください。[テクニカル ノート 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)します。  
  
 **BeginTrans**要求された同時実行とデータ ソースの機能によって、サーバー上のデータ レコードをロックも可能性があります。 データのロックについては、記事を参照して[レコード セット: レコードのロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)します。  
  
 ユーザー定義のトランザクションは、トピックで説明[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
 **BeginTrans**する一連のトランザクションをロールバックできます状態の確立 (反転)。 ロールバックの新しい状態を確立するために、現在のトランザクションをコミットし、呼び出す**BeginTrans**再度します。  
  
> [!CAUTION]
>  呼び出す**BeginTrans**呼び出さずにもう一度**CommitTrans**または**ロールバック**エラーが発生します。  
  
 呼び出す、 [CanTransact](#cantransact)ドライバーが特定のデータベースのトランザクションをサポートしているかどうかを調べます。 呼び出す必要があります[GetCursorCommitBehavior](#getcursorcommitbehavior)と[GetCursorRollbackBehavior](#getcursorrollbackbehavior)カーソル位置を保持のサポートの決定をします。  
  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="a-namebindparametersa--cdatabasebindparameters"></a><a name="bindparameters"></a>CDatabase::BindParameters  
 オーバーライド`BindParameters`を呼び出す前にパラメーターをバインドする必要がある場合[CDatabase::ExecuteSQL](#executesql)します。  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 `hstmt`  
 パラメーターをバインドする ODBC ステートメント ハンドル。  
  
### <a name="remarks"></a>コメント  
 この方法は、結果を必要としない場合に便利です、ストアド プロシージャからを設定します。  
  
 オーバーライドの中で呼び出して**SQLBindParameters**および関連するパラメーターを連結する ODBC 関数です。 MFC は、呼び出しの前に上書きを呼び出して`ExecuteSQL`します。 呼び出す必要はありません**SQLPrepare**です。`ExecuteSQL`呼び出し**SQLExecDirect**を破棄し、 **hstmt**、これは一度だけ使用します。  
  
##  <a name="a-namecancela--cdatabasecancel"></a><a name="cancel"></a>CDatabase::Cancel  
 実行中の非同期操作または&2; つ目のスレッドからのプロセスのいずれかのデータ ソースのキャンセルを要求するには、このメンバー関数を呼び出します。  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>コメント  
 MFC ODBC クラスが、非同期処理の使用を不要になったことに注意してください。非同期操作を実行する ODBC API 関数を直接に呼び出す必要があります[SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx)します。 詳細については、次を参照してください。[非同期実行](https://msdn.microsoft.com/library/ms713563.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namecantransacta--cdatabasecantransact"></a><a name="cantransact"></a>CDatabase::CanTransact  
 このメンバー関数を呼び出して、データベースはトランザクションを許可するかどうかを決定します。  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値を使用してこのレコード セット`CDatabase`オブジェクトは、トランザクションを許可する。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
##  <a name="a-namecanupdatea--cdatabasecanupdate"></a><a name="canupdate"></a>CDatabase::CanUpdate  
 判断するには、このメンバー関数を呼び出すかどうか、`CDatabase`オブジェクトの更新が許可されます。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDatabase`オブジェクトは、更新プログラムは、それ以外の場合 0 の場合、いずれかがあるかを示す渡される**TRUE**で`bReadOnly`を開くとき、`CDatabase`オブジェクトまたはデータがソース自体は読み取り専用です。 データ ソースが ODBC API 関数への呼び出しは読み取り専用**SQLGetInfo**の**SQL_DATASOURCE_READ_ONLY** "y"を返します。  
  
### <a name="remarks"></a>コメント  
 すべてのドライバーでは、更新をサポートします。  
  
##  <a name="a-namecdatabasea--cdatabasecdatabase"></a><a name="cdatabase"></a>CDatabase::CDatabase  
 `CDatabase` オブジェクトを構築します。  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築後に呼び出す必要があります、`OpenEx`または**開く**メンバー関数を指定したデータ ソースへの接続を確立します。  
  
 埋め込むできると便利な場合があります、`CDatabase`ドキュメント クラス内のオブジェクト。  
  
### <a name="example"></a>例  
 この例を使用して`CDatabase`で、 `CDocument`-クラスを派生します。  
  
 [!code-cpp[NVC_MFCDatabase&#9;](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase&#10;](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="a-nameclosea--cdatabaseclose"></a><a name="close"></a>CDatabase::Close  
 データ ソースから切断する場合は、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 関連付けられているすべてのレコード セットを閉じる必要があります、`CDatabase`オブジェクトのこのメンバー関数を呼び出す前にします。 **閉じる**は破棄しませんので、`CDatabase`オブジェクト、同じデータ ソースまたは別のデータ ソースに新しい接続を開くことによって、オブジェクトを再利用できます。  
  
 保留中のすべて`AddNew`または**編集**データベースを使用してレコード セットのステートメントはキャンセルされ、すべての保留中のトランザクションはロールバックされます。 すべてのレコード セットに依存して、`CDatabase`オブジェクトが定義されていない状態のままにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#12;](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="a-namecommittransa--cdatabasecommittrans"></a><a name="committrans"></a>CDatabase::CommitTrans  
 トランザクションを完了すると、このメンバー関数を呼び出します。  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>戻り値  
 更新プログラムが正常にコミットされた場合は 0 以外それ以外の場合 0 を返します。 場合**CommitTrans**失敗した場合、データ ソースの状態は未定義です。 その状態を確認するデータを確認する必要があります。  
  
### <a name="remarks"></a>コメント  
 トランザクションでは、一連の呼び出しの`AddNew`、**編集**、**削除**、および**更新**のメンバー関数、`CRecordset`オブジェクトへの呼び出しで開始した、 [(begintrans を)](#begintrans)メンバー関数。 **CommitTrans**トランザクションをコミットします。 既定では、更新プログラムすぐにコミットされます。呼び出す**BeginTrans**まで遅延する更新プログラムのコミットメントを原因**CommitTrans**が呼び出されます。  
  
 呼び出されるまで**CommitTrans** 、トランザクションを終了するには、呼び出すことができます、[ロールバック](#rollback)メンバー関数、トランザクションを中止し、元の状態で、データ ソースのままにします。 新しいトランザクションを開始する**BeginTrans**再度します。  
  
 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="a-nameexecutesqla--cdatabaseexecutesql"></a><a name="executesql"></a>CDatabase::ExecuteSQL  
 SQL コマンドを直接実行する必要がある場合は、このメンバー関数を呼び出します。  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSQL`  
 実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。 渡すことができます、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 Null で終わる文字列として、コマンドを作成します。 `ExecuteSQL`データ レコードは返しません。 レコードを操作する場合は、レコード セット オブジェクトを使用します。  
  
 ほとんどのデータ ソースのコマンドは、データを選択すると、新しいレコードの挿入、レコードを削除、およびレコードの編集用のコマンドをサポートしているレコード セット オブジェクトを通じて実行されます。 ただし、すべて ODBC 機能が直接サポート データベース クラスで直接 SQL 呼び出しを行うことがありますしなければならないように`ExecuteSQL`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#13;](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="a-namegetbookmarkpersistencea--cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>CDatabase::GetBookmarkPersistence  
 特定の操作の後で、レコードセット オブジェクトでのブックマークの永続性を判別するには、このメンバー関数を呼び出します。  
  
```  
DWORD GetBookmarkPersistence() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコードセット オブジェクトでブックマークが保持されている操作を識別するビットマスク。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 たとえば、`CRecordset::GetBookmark` を呼び出してから `CRecordset::Requery` を呼び出した場合、`GetBookmark` から取得されたブックマークは有効ではなくなっている場合があります。 `GetBookmarkPersistence` を呼び出してから `CRecordset::SetBookmark` を呼び出す必要があります。  
  
 `GetBookmarkPersistence` の戻り値として組み合わせることができるビットマスク値の一覧を次の表に示します。  
  
|ビットマスク値|ブックマークの永続性|  
|-------------------|--------------------------|  
|`SQL_BP_CLOSE`|ブックマークは有効の後、 **Requery**操作します。|  
|`SQL_BP_DELETE`|行のブックマークが後に有効では、**削除**行に対して操作します。|  
|`SQL_BP_DROP`|ブックマークは有効の後、**閉じる**操作します。|  
|`SQL_BP_SCROLL`|後、ブックマークは有効な**移動**操作します。 これは、`CRecordset::CanBookmark` によって返されるのと同様に、レコードセットでブックマークがサポートされているかどうかだけを示します。|  
|`SQL_BP_TRANSACTION`|トランザクションがコミットまたはロールバックされた後、ブックマークは有効です。|  
|`SQL_BP_UPDATE`|行のブックマークは後に有効な**更新**行に対して操作します。|  
|`SQL_BP_OTHER_HSTMT`|1 つのレコードセット オブジェクトに関連付けられたブックマークは、別のレコードセットで有効です。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 **SQLGetInfo**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ブックマークの詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。  
  
##  <a name="a-namegetconnecta--cdatabasegetconnect"></a><a name="getconnect"></a>Cdatabase::getconnect  
 このメンバー関数を呼び出すことで、`OpenEx` オブジェクトをデータ ソースに接続した `Open` または `CDatabase` の呼び出し時に使用された接続文字列を取得します。  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md)場合は、接続文字列を含む`OpenEx`または`Open`と呼ばれているそれ以外の場合、空の文字列です。  
  
### <a name="remarks"></a>コメント  
 参照してください[cdatabase::open](#open)接続文字列を作成する方法の詳細についてです。  
  
##  <a name="a-namegetcursorcommitbehaviora--cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>CDatabase::GetCursorCommitBehavior  
 判断するには、このメンバー関数を呼び出す方法、 [CommitTrans](#committrans)操作は、開いているレコード セット オブジェクトのカーソルに影響します。  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>戻り値  
 開いているレコード セット オブジェクトでのトランザクションの効果を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 次の表に、戻り値の`GetCursorCommitBehavior`と開いているレコード セットへの対応する影響します。  
  
|戻り値|CRecordset オブジェクトへの影響|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|呼び出す`CRecordset::Requery`トランザクションのコミットの直後です。|  
|`SQL_CB_DELETE`|呼び出す`CRecordset::Close`トランザクションのコミットの直後です。|  
|`SQL_CB_PRESERVE`|通常どおり続行`CRecordset`操作します。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 **SQLGetInfo**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
##  <a name="a-namegetcursorrollbackbehaviora--cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>CDatabase::GetCursorRollbackBehavior  
 判断するには、このメンバー関数を呼び出す方法、[ロールバック](#rollback)操作は、開いているレコード セット オブジェクトのカーソルに影響します。  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>戻り値  
 開いているレコード セット オブジェクトでのトランザクションの効果を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 次の表に、戻り値の`GetCursorRollbackBehavior`と開いているレコード セットへの対応する影響します。  
  
|戻り値|CRecordset オブジェクトへの影響|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|呼び出す`CRecordset::Requery`直後、トランザクションをロールバックします。|  
|`SQL_CB_DELETE`|呼び出す`CRecordset::Close`直後、トランザクションをロールバックします。|  
|`SQL_CB_PRESERVE`|通常どおり続行`CRecordset`操作します。|  
  
 この戻り値の詳細については、ODBC API 関数を参照してください。 **SQLGetInfo**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
##  <a name="a-namegetdatabasenamea--cdatabasegetdatabasename"></a><a name="getdatabasename"></a>CDatabase::GetDatabaseName  
 (データ ソースでは、「データベース」と呼ばれる、名前付きオブジェクトを定義) を指定した、現在接続しているデータベースの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)成功以外の場合は、データベース名を含む、空`CString`します。  
  
### <a name="remarks"></a>コメント  
 これはデータ ソース名 (DSN) で指定したのと同じ、`OpenEx`または**開く**を呼び出します。 どのような`GetDatabaseName`を返します。 は、ODBC によって異なります。 一般に、データベースは、テーブルのコレクションです。 このエンティティの名前が`GetDatabaseName`それを返します。  
  
 たとえば、見出しにこの名前を表示するがあります。 ODBC から名前を取得中にエラーが発生した場合`GetDatabaseName`は空白を返します**Cstring**します。  
  
##  <a name="a-nameisopena--cdatabaseisopen"></a><a name="isopen"></a>CDatabase::IsOpen  
 判断するには、このメンバー関数を呼び出すかどうか、`CDatabase`オブジェクトが現在のデータ ソースに接続しています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDatabase`オブジェクトが現在接続されている場合は 0 です。  
  
##  <a name="a-namemhdbca--cdatabasemhdbc"></a><a name="m_hdbc"></a>CDatabase::m_hdbc  
 」のには ODBC データ ソース接続へのパブリックのハンドルが含まれています"、「接続ハンドルです」。  
  
### <a name="remarks"></a>コメント  
 通常、する必要はありませんこのメンバー変数に直接アクセスします。 呼び出すときに、フレームワークがハンドルを割り当てる代わりに、`OpenEx`または**開く**します。 呼び出したときに、フレームワークは、ハンドルを解放、**削除**演算子で、`CDatabase`オブジェクトです。 なお、**閉じる**メンバー関数は、ハンドルを解放していません。  
  
 状況によっては、ただし、する必要があります、ハンドルを直接使用します。 たとえば、クラスではなく、直接、ODBC API 関数を呼び出す必要がある`CDatabase`、接続ハンドルをパラメーターとして渡す必要がある場合があります。 次のコード例を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#15;](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="a-nameonsetoptionsa--cdatabaseonsetoptions"></a><a name="onsetoptions"></a>CDatabase::OnSetOptions  
 含む SQL ステートメントを直接実行するときに、フレームワークが、このメンバー関数を呼び出す、`ExecuteSQL`メンバー関数。  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 `hstmt`  
 オプションが設定される ODBC ステートメント ハンドルです。  
  
### <a name="remarks"></a>コメント  
 `CRecordset::OnSetOptions`このメンバー関数も呼び出します。  
  
 `OnSetOptions`ログイン タイムアウト値を設定します。 前の呼び出しが発生した場合、`SetQueryTimeout`とメンバー関数`OnSetOptions`現在の値を反映してそれ以外の場合、既定値を設定します。  
  
> [!NOTE]
>  MFC 4.2 は、前に`OnSetOptions`もどちら snychronous または非同期処理モードを設定します。 MFC 4.2 以降では、すべての操作は同期されます。 非同期操作を実行する ODBC API 関数の直接呼び出しを行う必要があります**SQLSetPos**します。  
  
 オーバーライドする必要はありません`OnSetOptions`タイムアウト値を変更します。 クエリのタイムアウト値をカスタマイズする代わりに、`SetQueryTimeout`レコード セットを作成する前に`OnSetOptions`は新しい値を使用します。 値の設定は、すべてのレコード セットまたは SQL の直接呼び出しに対する後続の処理に適用されます。  
  
 オーバーライド`OnSetOptions`追加のオプションを設定する場合。 オーバーライドは基本クラスを呼び出す必要があります`OnSetOptions`前に、または ODBC API 関数を呼び出した後で**SQLSetStmtOption**します。 次のフレームワークの既定の実装に示すメソッド`OnSetOptions`します。  
  
##  <a name="a-nameopena--cdatabaseopen"></a><a name="open"></a>Cdatabase::open  
 このメンバー関数を呼び出して、新しく構築された初期化`CDatabase`オブジェクトです。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDSN`  
 データ ソース名が â € を指定"名前は ODBC で odbc データ ソース アドミニストレーターを登録します。 DSN の値がで指定されている場合`lpszConnect`(フォームに"DSN =\<データ ソース >") でもう一度指定してはなりませんが`lpszDSN`です。 この場合、`lpszDSN`べき**NULL**します。 それ以外の場合、渡せる**NULL**ユーザー、ユーザーがデータ ソースを選択できるデータ ソース ダイアログ ボックスに表示するかどうか。 詳細については、「解説」を参照してください。  
  
 `bExclusive`  
 クラス ライブラリのこのバージョンでサポートされていません。 このパラメーターがある場合、アサーションは失敗し現時点では、 **TRUE**します。 共有 (排他的ではない) で、データ ソースが常に開かれます。  
  
 `bReadOnly`  
 **TRUE**する場合は読み取り専用にして、データ ソースへの更新を禁止する接続です。 従属するすべてのレコード セットは、この属性を継承します。 既定値は**FALSE**します。  
  
 `lpszConnect`  
 接続文字列を指定します。 接続文字列を連結については、データ ソース名、データ ソース、ユーザー認証文字列 (パスワード、データ ソースでは、いずれかが必要な場合)、およびその他の情報に有効なユーザー ID を含む場合もあります。 接続文字列は、文字列"ODBC;"を前に付ける必要があります。(大文字でも小文字でも)。 "ODBC;"文字列を使用して、ODBC データ ソースに接続があることを示すこれは、クラス ライブラリの将来のバージョンが非 ODBC データ ソースをサポートと上位互換性のためです。  
  
 `bUseCursorLib`  
 **TRUE** ODBC カーソル ライブラリ DLL を読み込む場合に使用します。 カーソル ライブラリは、基になる、ODBC ドライバー (ドライバーによってサポートされる) 場合に、ダイナセットを使う場合の使用を有効に防ぐための機能の一部をマスクします。 カーソル ライブラリが読み込まれている場合をサポートするには、静的なスナップショットと順方向専用カーソルです。 既定値は**TRUE**します。 計画から直接 recordset オブジェクトを作成するかどうかは`CRecordset`そこから派生することがなくカーソル ライブラリをいないに読み込む必要があります。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、正常に接続します。それ以外の場合、ユーザーが選択した場合は 0 では、詳細な接続情報を確認するダイアログ ボックスが表示されたらをキャンセルします。 その他のすべてのケースでは、フレームワークは、例外をスローします。  
  
### <a name="remarks"></a>コメント  
 これを使用するにはレコード セット オブジェクトを構築する前に、データベース オブジェクトを初期化する必要があります。  
  
> [!NOTE]
>  呼び出す、 [OpenEx](#openex)メンバー関数は、データ ソースに接続し、データベース オブジェクトを初期化することをお勧めします。  
  
 場合では、パラメーター、**開く**呼び出しが接続するために十分な情報を含まない、ODBC ドライバーは、ユーザーから必要な情報を取得するダイアログ ボックスを開きます。 呼び出すと**開く**、接続文字列`lpszConnect`、個別に格納されている、`CDatabase`オブジェクトし、は、呼び出すことによって利用可能な[GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開く場合は、**を開く**パスワードなどのユーザーから情報を取得し、その情報、接続文字列を追加に渡す**開く**します。 時間を短縮できる再利用できるように、次を指定した接続文字列にアプリケーション呼び出しことができますか**開く**上、`CDatabase`オブジェクトです。  
  
 複数レベルのログイン認証の接続文字列を使用することもできます (それぞれ異なるを`CDatabase`オブジェクト) またはその他のデータ ソースに固有の情報を伝えるためにします。 接続文字列の詳細についてで第 5 章を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性です。 接続試行が失敗した場合、**開く**スロー、`CDBException`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#14;](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="a-nameopenexa--cdatabaseopenex"></a><a name="openex"></a>Cdatabase::openex  
 このメンバー関数を呼び出して、新しく構築された初期化`CDatabase`オブジェクトです。  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszConnectString`  
 ODBC 接続文字列を指定します。 これには、データ ソース名だけでなく、ユーザー ID やパスワードなどの省略可能なその他の情報が含まれます。 たとえば、"DSN = SQLServer_Source です。UID = SA;PWD = abc123"は有効な接続文字列。 渡す場合**NULL**の`lpszConnectString`、データ ソース ダイアログ ボックスでは、データ ソースの選択が求めるされます。  
  
 `dwOptions`  
 次の値の組み合わせを指定するビットマスクです。 既定値は 0、書き込みアクセス権と共有するには、ODBC カーソル ライブラリ DLL は読み込まれず、接続するために十分な情報がない場合にのみ、ODBC の接続 ダイアログ ボックスが表示されます、データベースとして開かれることを意味します。  
  
- **CDatabase::openExclusive**クラス ライブラリのこのバージョンでサポートされていません。 共有 (排他的ではない) で、データ ソースが常に開かれます。 現時点では、このオプションを指定すると、アサーションが失敗します。  
  
- **CDatabase::openReadOnly**読み取り専用とデータ ソースを開きます。  
  
- **読み込む**ODBC カーソル ライブラリ DLL を読み込めません。 カーソル ライブラリは、基になる、ODBC ドライバー (ドライバーによってサポートされる) 場合に、ダイナセットを使う場合の使用を有効に防ぐための機能の一部をマスクします。 カーソル ライブラリが読み込まれている場合をサポートするには、静的なスナップショットと順方向専用カーソルです。 計画から直接 recordset オブジェクトを作成するかどうかは`CRecordset`そこから派生することがなくカーソル ライブラリをいないに読み込む必要があります。  
  
- **CDatabase::noOdbcDialog**十分な接続情報を提供するかどうかに関係なく、ODBC の接続 ダイアログ ボックスは表示されません。  
  
- **CDatabase::forceOdbcDialog**常に ODBC 接続 ダイアログ ボックスを表示します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、正常に接続します。それ以外の場合、ユーザーが選択した場合は 0 では、詳細な接続情報を確認するダイアログ ボックスが表示されたらをキャンセルします。 その他のすべてのケースでは、フレームワークは、例外をスローします。  
  
### <a name="remarks"></a>コメント  
 これを使用するにはレコード セット オブジェクトを構築する前に、データベース オブジェクトを初期化する必要があります。  
  
 場合、`lpszConnectString`内のパラメーター、`OpenEx`呼び出しに接続するために十分な情報が含まれていない ODBC ドライバーにより、ユーザーから必要な情報を取得するダイアログ ボックスが表示されるため、設定していない限り場合、 **CDatabase::noOdbcDialog**または**CDatabase::forceOdbcDialog**で、`dwOptions`パラメーター。 呼び出すと`OpenEx`、接続文字列`lpszConnectString`、個別に格納されている、`CDatabase`オブジェクトで、使用を呼び出して、 [GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開く場合は、`OpenEx`パスワードなどのユーザーから情報を取得し、その情報に渡す接続文字列に追加する`OpenEx`です。 接続文字列を渡すことができます再利用できるように、次の時間をアプリケーション呼び出しすることができますか`OpenEx`上、`CDatabase`オブジェクトです。  
  
 複数レベルのログイン認証の接続文字列を使用することもできます (それぞれ異なるを`CDatabase`オブジェクト) またはその他のデータ ソースに固有の情報を伝えるためにします。 接続文字列の詳細についてで第 6 章を参照してください、 *ODBC プログラマ リファレンス*します。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性です。 接続の試行が失敗した場合、`OpenEx`スロー、`CDBException`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#11;](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="a-namerollbacka--cdatabaserollback"></a><a name="rollback"></a>CDatabase::Rollback  
 トランザクション中に行われた変更を反転するには、このメンバー関数を呼び出します。  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>戻り値  
 トランザクションが正常に取り消された; 場合 0 以外。それ以外の場合 0 を返します。 場合、**ロールバック**呼び出しが失敗する、データ ソースとトランザクションの状態は未定義です。 場合**ロールバック**0 を返し、状態を確認するデータ ソースを確認する必要があります。  
  
### <a name="remarks"></a>コメント  
 すべて`CRecordset``AddNew`、**編集**、**削除**、および**更新**最後に実行されるコール[(begintrans を)](#begintrans)呼び出しの時点に存在していた状態にロールバックされます。  
  
 呼び出した後**ロールバック**、トランザクションが終了し、呼び出す必要があります**BeginTrans**別のトランザクション用にもう一度です。 呼び出される前に行われたレコード**(begintrans を)**レコードになり、現在もう一度後**ロールバック**します。  
  
 ロールバック後ロールバック前に、の現在のレコードを最新の状態します。 レコード セットとロールバックした後、データ ソースの状態に関する詳細については、記事を参照して[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
### <a name="example"></a>例  
  記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="a-namesetlogintimeouta--cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>CDatabase::SetLoginTimeout  
 このメンバー関数 â € を呼び出す"を呼び出す前に`OpenEx`または**開く**â €"ソースの接続タイムアウトになるまで実行されたデータに許容される秒数の既定をオーバーライドします。  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwSeconds`  
 タイムアウトする接続の試行までの秒数。  
  
### <a name="remarks"></a>コメント  
 接続の試行には、たとえば、データベース管理システムが使用できない場合は、タイムアウトが可能性があります。 呼び出す**SetLoginTimeout** 、初期化されていないを構築してから`CDatabase`オブジェクトしますが、前に呼び出して`OpenEx`または**開く**します。  
  
 ログイン タイムアウトの既定値は、15 秒です。 すべてのデータ ソースでは、ログイン タイムアウト値を指定する機能をサポートします。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力でもない例外を取得します。 値が 0 の場合「無制限」。  
  
##  <a name="a-namesetquerytimeouta--cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDatabase::SetQueryTimeout  
 後続の処理を接続されているデータ ソースのタイムアウトになるまでの秒数の既定をオーバーライドする場合は、このメンバー関数を呼び出します。  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwSeconds`  
 タイムアウトするクエリの試行までの秒数。  
  
### <a name="remarks"></a>コメント  
 操作は、ネットワーク アクセスの問題、過剰なクエリの処理時間によるタイムアウト可能性があります。 呼び出す`SetQueryTimeout`またはレコード セットの前に、レコード セットを開く前に`AddNew`、**更新**または**削除**メンバー関数をクエリのタイムアウト値を変更する場合。 後続のすべての設定に影響**開く**、 `AddNew`、**更新**と**削除**これに関連付けられているすべてのレコード セットへの呼び出し`CDatabase`オブジェクトです。 開いた後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、その後**移動**操作は、新しい値を使用しないでください。  
  
 クエリ タイムアウトの既定値は、15 秒です。 すべてのデータ ソースでは、クエリのタイムアウト値を設定する機能をサポートします。 クエリのタイムアウト値は 0 を設定する場合は、タイムアウトは行われません。データ ソースとの通信が応答を停止します。 この動作は、開発時に便利な可能性があります。 データ ソースがタイムアウトをサポートしていない場合は、トレース出力でもない例外を取得します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)

