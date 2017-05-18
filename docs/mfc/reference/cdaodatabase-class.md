---
title: "CDaoDatabase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], DAO
- CDaoDatabase class, vs. CDatabase class
- CDaoDatabase class, and workspace
- CDaoDatabase class
- CDatabase class, vs. CDaoDatabase class
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c173ea0c0132752c08504053d9b00cdec8d3f69b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaodatabase-class"></a>CDaoDatabase クラス
それを通じてデータを操作することのできるデータベースへの接続を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` オブジェクトを構築します。 呼び出す**開く**オブジェクトをデータベースに接続します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|データベースがトランザクションをサポートしている場合は&0; 以外を返します。|  
|[CDaoDatabase::CanUpdate](#canupdate)|場合は&0; 以外の値を返し、`CDaoDatabase`オブジェクトが更新可能な (いない読み取り専用)。|  
|[CDaoDatabase::Close](#close)|データベース接続を閉じます。|  
|[CDaoDatabase::Create](#create)|基になる DAO データベース オブジェクトを作成し、初期化、`CDaoDatabase`オブジェクトです。|  
|[CDaoDatabase::CreateRelation](#createrelation)|データベースのテーブル間の新しいリレーションシップを定義します。|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|データベースのクエリ定義のコレクションに保存されているクエリ定義オブジェクトを削除します。|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|データベースのテーブル間の既存のリレーションシップを削除します。|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|データベース内のテーブルの定義を削除します。 これは、実際のテーブルとそのすべてのデータを削除します。|  
|[CDaoDatabase::Execute](#execute)|アクション クエリを実行します。 呼び出す**Execute**の結果を返すクエリは、例外をスローします。|  
|[CDaoDatabase::GetConnect](#getconnect)|接続に使用される接続文字列を返す、`CDaoDatabase`データベースへのオブジェクト。 ODBC に使用されます。|  
|[CDaoDatabase::GetName](#getname)|現在使用中のデータベースの名前を返します。|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|データベースに対して定義されているクエリの数を返します。|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|データベースで定義されている、指定されたクエリに関する情報を返します。|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|クエリ操作をデータベースの後の秒数を返しますが、タイムアウトします。 後続のすべての影響を開く、新規追加、更新、および操作と ODBC データ ソースに対して他の操作を次のように (のみ) 編集**Execute**呼び出しです。|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|最後の更新によって影響を受けるレコードの数を返します。 は、編集、または、操作を追加またはへの呼び出しによって**Execute**します。|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|データベース内のテーブル間で定義されているリレーションシップの数を返します。|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|データベース内のテーブル間で定義されているリレーションシップに関する情報を返します。|  
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|データベースで定義されているテーブルの数を返します。|  
|[Cdaodatabase::gettabledefinfo](#gettabledefinfo)|データベース内の指定されたテーブルに関する情報を返します。|  
|[CDaoDatabase::GetVersion](#getversion)|データベースに関連付けられているデータベース エンジンのバージョンを返します。|  
|[CDaoDatabase::IsOpen](#isopen)|場合は&0; 以外の値を返し、`CDaoDatabase`オブジェクトが現在のデータベースに接続されています。|  
|[CDaoDatabase::Open](#open)|データベースへの接続を確立します。|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|セットのクエリ (ODBC データ ソースのみ) の操作をデータベースの後の秒数はタイムアウトします。 開く新規追加、更新、および削除の各操作に後続のすべてに影響します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|基になる DAO データベース オブジェクトへのポインター。|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|ポインター、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトでは、データベースを含み、そのトランザクション領域を定義します。|  
  
## <a name="remarks"></a>コメント  
 サポートされているデータベース形式については、次を参照してください。、 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname)メンバー関数。 1 つまたは複数を持てる`CDaoDatabase`特定の"ワークスペースで、"によって表されるオブジェクトを一度にアクティブ、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトです。 ワークスペースは、データベースのコレクションと呼ばれる、開いているデータベース オブジェクトのコレクションを保持します。  
  
> [!NOTE]
>  MFC DAO データベース クラスは、ODBC に基づいて MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 クラス`CDaoDatabase`の ODBC クラスに似たインターフェイスを提供[CDatabase](../../mfc/reference/cdatabase-class.md)します。 その主な違いは`CDatabase`オープン データベース コネクティビティ (ODBC) と ODBC ドライバーを通じてその DBMS のデータベースにアクセスします。 `CDaoDatabase`Microsoft Jet データベース エンジンに基づくデータ アクセス オブジェクト (DAO) を通じてデータにアクセスします。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含むデータにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="usage"></a>使用方法  
 レコード セット オブジェクトを作成するときに、データベース オブジェクトを暗黙的に作成できます。 データベース オブジェクトを明示的に作成することもできます。 既存のデータベースを使用して明示的に使用する`CDaoDatabase`次のいずれかの操作します。  
  
-   構築、`CDaoDatabase`開いたへのポインターを渡して、オブジェクト[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトです。  
  
-   作成したり、 `CDaoDatabase` (MFC では、一時的なワークスペースのオブジェクトを作成します) ワークスペースを指定しないでオブジェクトです。  
  
 新しい Microsoft Jet を作成する (。MDB) データベースを作成、`CDaoDatabase`オブジェクトと呼び出しの[作成](#create)メンバー関数。 *いない*を呼び出す**開く**後**作成**します。  
  
 既存のデータベースを開くには、するために作成、`CDaoDatabase`オブジェクトと呼び出しの[開く](#open)メンバー関数。  
  
 これらの手法のいずれかにより、DAO データベース オブジェクトをワークスペース データベースのコレクションに追加し、データへの接続を開きます。 構築するときに[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、[どちら](../../mfc/reference/cdaotabledef-class.md)、または[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)接続されているデータベースで動作しているオブジェクトへのポインターをこれらのオブジェクトのコンス トラクターに渡す、`CDaoDatabase`オブジェクトです。 接続を使用してが完了したらを呼び出す、[閉じる](#close)メンバー関数し、破棄、`CDaoDatabase`オブジェクトです。 **閉じる**閉じられていないすべてのレコード セットを閉じます。  
  
## <a name="transactions"></a>トランザクション  
 データベース トランザクションの処理がワークスペース レベルで提供されている — を参照してください、 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)、 [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)と[ロールバック](../../mfc/reference/cdaoworkspace-class.md#rollback)クラスのメンバー関数`CDaoWorkspace`します。  
  
## <a name="odbc-connections"></a>ODBC 接続  
 ODBC データ ソースを使用するための推奨方法は、Microsoft Jet に外部テーブルをアタッチする (。MDB) データベース。  
  
## <a name="collections"></a>コレクション  
 各データベースでは、テーブル定義、クエリ定義、レコード セット、およびリレーションシップ オブジェクトの独自のコレクションを保持します。 クラス`CDaoDatabase`これらのオブジェクトを操作するためのメンバー関数が用意されています。  
  
> [!NOTE]
>  オブジェクトが DAO、格納されているは、MFC データベース オブジェクトにありません。 MFC では、テーブル定義、クエリ定義、およびレコード セット オブジェクトですが、リレーションシップ オブジェクトではなくクラスを提供します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="cantransact"></a>CDaoDatabase::CanTransact  
 このメンバー関数を呼び出して、データベースはトランザクションを許可するかどうかを決定します。  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>戻り値  
 データベースがトランザクションをサポートしている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 トランザクションは、データベースのワークスペースで管理されます。  
  
##  <a name="canupdate"></a>CDaoDatabase::CanUpdate  
 判断するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトの更新が許可されます。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDaoDatabase`オブジェクトは、更新プログラムは、それ以外の場合 0 の場合、いずれかがあるかを示す渡される**TRUE**で`bReadOnly`を開くとき、`CDaoDatabase`オブジェクトまたはデータベース自体には読み取り専用です。 参照してください、[開く](#open)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 データベースの更新方法については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
##  <a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase  
 `CDaoDatabase` オブジェクトを構築します。  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWorkspace*  
 ポインター、`CDaoWorkspace`新しいデータベース オブジェクトを格納するオブジェクト。 既定値を受け入れる場合**NULL**、コンス トラクターは、作成、一時的な`CDaoWorkspace`既定 DAO のワークスペースを使用するオブジェクト。 使用してワークスペース オブジェクトへのポインターを取得、 [m_pWorkspace](#m_pworkspace)データ メンバーです。  
  
### <a name="remarks"></a>コメント  
 新しい Microsoft Jet を作成する場合は、オブジェクトを構築した後 (します。MDB) データベース、オブジェクトの[作成](#create)メンバー関数。 オブジェクトを呼び出し、既存のデータベースを開く場合は、代わりに、[開く](#open)メンバー関数。  
  
 オブジェクトを終了するときに呼び出す必要があります、[閉じる](#close)メンバーに機能し、破棄、`CDaoDatabase`オブジェクトです。  
  
 埋め込むできると便利な場合があります、`CDaoDatabase`ドキュメント クラス内のオブジェクト。  
  
> [!NOTE]
>  A`CDaoDatabase`を開いた場合、オブジェクトは暗黙的に作成されるも、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを既存のポインターを渡さずに`CDaoDatabase`オブジェクトです。 レコード セット オブジェクトを閉じると、このデータベース オブジェクトが閉じられます。  
  
##  <a name="close"></a>CDaoDatabase::Close  
 このメンバー関数を呼び出して、データベースから切断し、開いているレコード セット、テーブル定義、およびデータベースに関連付けられているクエリを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出す前にこれらのオブジェクトを手動で閉じることをお勧めします。 閉じる、`CDaoDatabase`オブジェクトを関連するデータベース コレクションから削除[ワークスペース](../../mfc/reference/cdaoworkspace-class.md)します。 **閉じる**は破棄しませんので、`CDaoDatabase`オブジェクトを同じデータベースまたは別のデータベースを開き、オブジェクトを再利用することができます。  
  
> [!CAUTION]
>  呼び出す、[更新](../../mfc/reference/cdaorecordset-class.md#update)メンバー関数 (保留中の編集がある場合) および**閉じる**データベースを終了する前に開いているレコード セット オブジェクトのすべてのメンバー関数。 宣言する関数を終了する場合は、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)または`CDaoDatabase`スタックで、オブジェクトをデータベースが閉じ、未保存の変更は失われる、すべて保留中のトランザクションはロールバック、および、データへの保留中の編集は失われます。  
  
> [!CAUTION]
>  すべてのレコード セット オブジェクトが、開いている間、データベース オブジェクトを閉じようとするとワークスペースに所属するデータベース オブジェクトが開いている間、workspace オブジェクトを終了しようとする場合や、そのレコード セット オブジェクトが閉じられ、保留中の更新または編集をすべてロールバックされます。 所属するデータベース オブジェクトが開いている間、workspace オブジェクトを終了しようとすると、操作は、閉じられていないレコード セット オブジェクトになる可能性があります、その特定のワークスペース オブジェクトに属するすべてのデータベース オブジェクトを終了します。 データベース オブジェクトを終了しない場合、MFC は、デバッグ ビルドでは、アサーション エラーを報告します。  
  
 データベース オブジェクトが、関数のスコープ外部で定義された関数を閉じずに終了する場合は、データベース オブジェクトは明示的に閉じるまで開いたままとまたはが定義されているモジュールがスコープ外です。  
  
##  <a name="create"></a>CDaoDatabase::Create  
 新しい Microsoft Jet を作成する (。MDB) データベースを作成した後、このメンバー関数を呼び出して、`CDaoDatabase`オブジェクトです。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 作成しているデータベース ファイルの名前を表す文字列式です。 できますの完全なパスとファイル名など、"c:\\\MYDB します。MDB"です。 名を指定する必要があります。 場合は、ファイル名拡張子を指定しないとします。MDB が追加されます。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合も指定できます、ネットワーク パスなど、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB"です。 Microsoft Jet のみ (します。MDB) データベース ファイルは、このメンバー関数を使用して作成できます。 (ために、文字列リテラルで二重の円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
 `lpszLocale`  
 データベースを作成するための照合順序を指定するために使用する文字列式です。 既定値は**dbLangGeneral**します。 指定できる値は次のとおりです。  
  
- **dbLangGeneral**英語、ドイツ語、フランス語、ポルトガル語、イタリア語、および最新のスペイン語  
  
- **dbLangArabic**アラビア語  
  
- **dbLangCyrillic**ロシア語  
  
- **dbLangCzech**チェコ語  
  
- **dbLangDutch**オランダ語  
  
- **dbLangGreek**ギリシャ語  
  
- **dbLangHebrew**ヘブライ語  
  
- **dbLangHungarian**ハンガリー語  
  
- **dbLangIcelandic**アイスランド語  
  
- **dbLangNordic**スカンジナビア語 (Microsoft Jet データベース エンジンのバージョン 1.0 のみ)  
  
- **dbLangNorwdan**ノルウェー語、デンマーク語  
  
- **dbLangPolish**ポーランド語  
  
- **dbLangSpanish**従来のスペイン語  
  
- **dbLangSwedfin**スウェーデン語、フィンランド語  
  
- **dbLangTurkish**トルコ語  
  
 `dwOptions`  
 1 つまたは複数のオプションを示す整数。 指定できる値は次のとおりです。  
  
- **dbEncrypt**暗号化されたデータベースを作成します。  
  
- **dbVersion10** Microsoft Jet データベースのバージョン 1.0 でデータベースを作成します。  
  
- **dbVersion11** Microsoft Jet データベースのバージョン 1.1 でデータベースを作成します。  
  
- **dbVersion20** Microsoft Jet データベースのバージョン 2.0 でデータベースを作成します。  
  
- **dbVersion30** Microsoft Jet データベースのバージョン 3.0 でデータベースを作成します。  
  
 暗号化の定数を省略した場合は、暗号化されていないデータベースが作成されます。 1 つだけのバージョンの定数を指定できます。 バージョンの定数を省略した場合は、Microsoft Jet データベースのバージョン 3.0 を使用するデータベースが作成されます。  
  
> [!CAUTION]
>  データベースが暗号化されていない場合、可能な場合でもあるデータベースを構成するバイナリ ディスク ファイルを直接読み取るユーザー/パスワード セキュリティを実装します。  
  
### <a name="remarks"></a>コメント  
 **作成**データベース ファイルと基になる DAO データベース オブジェクトを作成し、C++ オブジェクトを初期化します。 オブジェクトは、関連付けられているワークスペースのデータベース コレクションに追加されます。 データベース オブジェクトは、開いている状態です。呼び出す必要はありません**開く**後**作成**します。  
  
> [!NOTE]
>  **作成**、Microsoft Jet のみを作成することができます (します。MDB) データベース。 ISAM データベースまたは ODBC データベースを作成することはできません。  
  
##  <a name="createrelation"></a>CDaoDatabase::CreateRelation  
 このメンバー関数を呼び出して、データベースのプライマリ テーブルに&1; つ以上のフィールドと外部テーブル (データベース内の別のテーブル) 内の&1; つまたは複数のフィールドの間の関係を確立します。  
  
```  
void CreateRelation(
    LPCTSTR lpszName,  
    LPCTSTR lpszTable,  
    LPCTSTR lpszForeignTable,  
    long lAttributes,  
    LPCTSTR lpszField,  
    LPCTSTR lpszForeignField);  
  
void CreateRelation(CDaoRelationInfo& relinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 Relation オブジェクトの一意の名前。 名前は、先頭を英字にする必要があり、最大 40 文字を含めることができます。 数字を含めることができ、アンダー スコア文字しますが、区切り記号やスペースを含めることはできません。  
  
 `lpszTable`  
 リレーションシップの主テーブルの名前。 MFC が型の例外をスローする場合は、テーブルが存在しない[CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
 `lpszForeignTable`  
 リレーションシップの外部キー テーブルの名前。 MFC が型の例外をスローする場合は、テーブルが存在しない`CDaoException`します。  
  
 `lAttributes`  
 リレーションシップの種類に関する情報を含む long 値です。 この値を使用すると、その他の処理の間の参照整合性を適用します。 ビットごとの OR 演算子を使用することができます ( **|**) である限り意味を兼ね備えているため)、次の値のいずれかを結合します。  
  
- **dbRelationUnique**リレーションシップが一対一です。  
  
- **dbRelationDontEnforce**関係はありません (参照整合性がありません) が適用されます。  
  
- **dbRelationInherited**リレーションシップが&2; つの接続されているテーブルを含む固定データベースに存在します。  
  
- **これら**が連鎖的に更新プログラム (連鎖については、「解説」を参照してください)。  
  
- **dbRelationDeleteCascade**が連鎖的に削除します。  
  
 *lpszField*  
 主テーブル内のフィールドの名前を表す null で終わる文字列へのポインター (付けた`lpszTable`)。  
  
 *lpszForeignField*  
 外部テーブル内のフィールドの名前を表す null で終わる文字列へのポインター (付けた`lpszForeignTable`)。  
  
 *relinfo*  
 参照、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)を作成する関係に関する情報を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リレーションシップには、クエリ、または外部データベースから接続されているテーブルを含めることはできません。  
  
 リレーションシップには&2; つのテーブルの&1; つのフィールドが含まれている場合は、関数の最初のバージョンを使用します。 リレーションシップに複数のフィールドが含まれている場合は、2 番目のバージョンを使用します。 リレーションシップ内のフィールドの最大数は 14 です。  
  
 この操作は、基になる DAO リレーションシップ オブジェクトを作成が、これはリレーションシップ オブジェクトの MFC のカプセル化がクラス内に含まれるために、MFC 実装の細部`CDaoDatabase`します。 MFC では、リレーションシップのクラスを提供していません。  
  
 連鎖操作をアクティブ化するオブジェクトの属性リレーションシップを設定すると、データベース エンジンが、自動的に更新や、関連の主キー テーブルに変更が加えられたときにその他の&1; つまたは複数のテーブル内のレコードを削除します。  
  
 たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除すると、その顧客に関連する Orders テーブル内のレコードも削除されます。 さらに、連鎖削除の Orders テーブルとその他のテーブル間のリレーションシップを確立すると、これらのテーブルからレコードは自動的に削除 Customers テーブルからレコードを削除します。  
  
 関連情報については、DAO ヘルプの「CreateRelation メソッド」を参照してください。  
  
##  <a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef  
 指定したクエリ定義を削除するには、このメンバー関数を呼び出す: 保存されたクエリ: から、`CDaoDatabase`オブジェクトのクエリ定義のコレクション。  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除するのには、保存済みのクエリの名前。  
  
### <a name="remarks"></a>コメント  
 その後、そのクエリは、不要になったデータベースに定義されます。  
  
 クエリ定義のオブジェクトを作成する方法の詳細については、クラスを参照してください。 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)します。 クエリ定義オブジェクトが特定の関連付け`CDaoDatabase`オブジェクトを構築するとき、`CDaoQueryDef`オブジェクト、データベース オブジェクトへのポインターを渡します。  
  
##  <a name="deleterelation"></a>CDaoDatabase::DeleteRelation  
 データベース オブジェクトの関係のコレクションから既存のリレーションシップを削除するには、このメンバー関数を呼び出します。  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除するリレーションシップの名前。  
  
### <a name="remarks"></a>コメント  
 その後、不要になったリレーションシップが存在します。  
  
 関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。  
  
##  <a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef  
 このメンバー関数を呼び出して、指定したテーブルとすべてのデータの削除、`CDaoDatabase`オブジェクトのテーブル定義のコレクション。  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 削除するテーブル定義の名前です。  
  
### <a name="remarks"></a>コメント  
 その後、そのテーブルは、不要になったデータベースに定義されます。  
  
> [!NOTE]
>  非常にならないように注意するシステム テーブルを削除します。  
  
 テーブル定義のオブジェクトを作成する方法の詳細については、クラスを参照してください。[どちら](../../mfc/reference/cdaotabledef-class.md)します。 テーブル定義のオブジェクトが特定の関連付け`CDaoDatabase`オブジェクトを構築するとき、`CDaoTableDef`オブジェクト、データベース オブジェクトへのポインターを渡します。  
  
 関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。  
  
##  <a name="execute"></a>CDaoDatabase::Execute  
 このメンバー関数を呼び出してアクション クエリを実行するか、データベースで SQL ステートメントを実行します。  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSQL`  
 実行する有効な SQL コマンドを含む null で終わる文字列へのポインター。  
  
 `nOptions`  
 クエリの整合性に関連するオプションを指定する整数。 ビットごとの OR 演算子を使用することができます ( **|**) を自由に、次の定数を組み合わせる (意味指定 — たとえば、組み合わせることができません**組み合わせて**で**指定できます**)。  
  
- **dbDenyWrite**他のユーザーへの書き込み権限を拒否します。  
  
- **組み合わせて**(既定値) の一貫性のない更新プログラムです。  
  
- **指定できます**一貫性のある更新します。  
  
- **dbSQLPassThrough** SQL パススルーします。 原因で処理するために ODBC データ ソースに渡される SQL ステートメント。  
  
- **dbFailOnError**エラーが発生した場合は、更新プログラムをロールバックします。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合は、実行時エラーを生成します。  
  
> [!NOTE]
>  両方**組み合わせて**と**指定できます**が含まれていますか、結果が、既定でどちらが含まれている場合。 これらの定数の詳細については、DAO ヘルプの「メソッドの実行」を参照してください。  
  
### <a name="remarks"></a>コメント  
 **実行**操作クエリ、または結果を返さない SQL パススルー クエリに対してのみ機能します。 レコードを返す select クエリは機能しません。  
  
 定義とアクションのクエリの詳細については、「アクションのクエリ」DAO ヘルプの「メソッドの実行」トピックを参照してください。  
  
> [!TIP]
>  正しい構文の SQL ステートメントと適切なアクセス許可を与え、 **Execute**メンバー関数はでも失敗しないかどうか、1 行を変更または削除します。 そのため、常に使用、 **dbFailOnError**オプションを使用する場合、 **Execute**更新プログラムを実行またはクエリを削除するメンバー関数。 このオプションは、型の例外をスローする MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)し場合、影響を受けたレコードのいずれかがロックされているとできませんを更新または削除は、すべての正常な変更をロールバックします。 常に呼び出すことのできる注`GetRecordsAffected`に影響を受けたレコードの数を参照してください。  
  
 呼び出す、 [GetRecordsAffected](#getrecordsaffected)最新によって影響を受けたレコードの数を決定するデータベース オブジェクトのメンバー関数**Execute**呼び出します。 たとえば、`GetRecordsAffected`削除、更新、またはアクション クエリを実行するときに挿入されるレコードの数に関する情報を返します。 返されるカウントを重ねて表示を更新または削除時に関連付けられたテーブル内の変更が反映反映されません。  
  
 **実行**はレコード セットを返しません。 使用して**Execute**レコードを選択するクエリに MFC 型の例外をスローすると、`CDaoException`です。 (がない`ExecuteSQL`メンバー関数に似ています`CDatabase::ExecuteSQL`)。  
  
##  <a name="getconnect"></a>CDaoDatabase::GetConnect  
 接続に使用される接続文字列を取得するには、このメンバー関数を呼び出す、 `CDaoDatabase` ODBC または ISAM データベースにオブジェクトです。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 接続文字列の場合は[開く](#open)ODBC データ ソースで正常に呼び出されているそれ以外の場合、空の文字列です。 Microsoft Jet 用 (します。MDB) データベースの場合は、文字列は常に空で使用するために設定していない場合、 **dbSQLPassThrough**と共に使用するオプション、 [Execute](#execute)メンバー関数、またはレコード セットを開くときに使用します。  
  
### <a name="remarks"></a>コメント  
 文字列は、開いているデータベースまたはパススルー クエリで使用されるデータベースのソースに関する情報を提供します。 接続文字列は、データベースの型指定子は、セミコロン (;) で区切られた&0; 個以上のパラメーターで構成されます。  
  
> [!NOTE]
>  MFC DAO クラスを使用して ODBC 経由でデータ ソースに接続することは、接続されているテーブルを使用して接続するよりも非効率です。  
  
> [!NOTE]
>  接続文字列を使用して、ODBC や必要に応じて、特定の ISAM ドライバーへの追加情報を渡します。 を使用されません。MDB データベース。 Microsoft Jet データベースのベース テーブルでは、接続文字列は空の文字列 ("") として使用する場合、SQL パススルー クエリの戻り値を上記で説明されている以外です。  
  
 参照してください、[開く](#open)接続文字列を作成する方法の詳細については、メンバー関数。 接続文字列を設定した後、**開く**呼び出し、後で使える型、パス、データベースのユーザー ID、パスワード、または ODBC データ ソースを決定する設定を確認します。  
  
##  <a name="getname"></a>CDaoDatabase::GetName  
 これは既存のデータベース ファイルの名前で現在開いているデータベースの名前または登録されている ODBC データ ソースの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、データベースのファイルの名前と完全なパスそれ以外の場合、空[CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合も、ネットワーク パスを指定できます: たとえば、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"です。 (ために、文字列リテラルで二重の円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
 たとえば、見出しにこの名前を表示するがあります。 名前の取得中にエラーが発生する場合、MFC は型の例外をスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
> [!NOTE]
>  パフォーマンス向上のため外部データベースはアクセスするときをお勧め外部データベース テーブルは、Microsoft Jet データベースに接続する (。MDB) データ ソースに直接接続するのではなく。  
  
 データベースの種類は、ファイルまたはディレクトリに、次のように、パスが指すで示されます。  
  
|ポインターをパス名。|データベースの種類|  
|--------------------------|-------------------|  
|.MDB ファイル|Microsoft Jet データベース (Access)|  
|格納するディレクトリ。DBF ファイル|dBASE データベース|  
|格納するディレクトリ。XLS ファイル|Microsoft Excel データベース|  
|格納するディレクトリ。PDX ファイル|Paradox データベース|  
|データベース ファイルを適切に書式設定されたテキストを含むディレクトリ|テキスト形式のデータベース|  
  
 SQL Server、Oracle などの ODBC データベースのデータベースの接続文字列は、ODBC によって登録されているデータ ソース名 (DSN) を識別します。  
  
##  <a name="getquerydefcount"></a>CDaoDatabase::GetQueryDefCount  
 データベースのクエリ定義のコレクションで定義されているクエリの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベースで定義されているクエリの数。  
  
### <a name="remarks"></a>コメント  
 `GetQueryDefCount`QueryDefs コレクション内のすべてのクエリ定義をループする必要がある場合に便利です。 コレクション内の特定のクエリに関する情報を取得するには、次を参照してください。 [GetQueryDefInfo](#getquerydefinfo)します。  
  
##  <a name="getquerydefinfo"></a>CDaoDatabase::GetQueryDefInfo  
 さまざまな種類のデータベースで定義されたクエリに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetQueryDefInfo(
    int nIndex,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetQueryDefInfo(
    LPCTSTR lpszName,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、データベースのクエリ定義のコレクションで定義済みのクエリのインデックス。  
  
 *querydefinfo*  
 参照、 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)オブジェクトを必要な情報を返します。  
  
 `dwInfoOptions`  
 取得するレコード セットに関する情報を指定するオプションです。 使用可能なオプションは、レコード セットを返す関数が何もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、型  
  
- `AFX_DAO_SECONDARY_INFO`プライマリ情報に加えて: 作成日付、最終更新日付、レコードを返す、更新可能  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報に加えて: SQL の接続で、補足  
  
 `lpszName`  
 名前で検索する場合、データベースで定義されたクエリの名前を含む文字列。  
  
### <a name="remarks"></a>コメント  
 クエリは、データベースのクエリ定義のコレクション内のインデックスまたはクエリの名前のいずれかを選択できるように、関数の&2; つのバージョンが提供されます。  
  
 返される情報の詳細については*querydefinfo*を参照してください、 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルの情報を要求すると、その情報も同様のレベルを取得できます。  
  
##  <a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout  
 現在接続されているデータベースに対する後続の処理がタイムアウトするまで許可する秒数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 秒のタイムアウト値を格納している短整数。  
  
### <a name="remarks"></a>コメント  
 操作は、ネットワーク アクセスの問題、過剰なクエリの処理時間によるタイムアウト可能性があります。 すべてのオープン状態に影響を与える設定が有効になっているときに、新規追加、更新、および削除操作に関連付けられたすべてのレコード セットに`CDaoDatabase`オブジェクトです。 現在のタイムアウト設定を変更するにを呼び出して[SetQueryTimeout](#setquerytimeout)します。 開いた後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、その後[移動](../../mfc/reference/cdaorecordset-class.md#move)操作は、新しい値を使用しないでください。 既定値は、データベース エンジンの初期化時に初期設定されます。  
  
 クエリ タイムアウトの既定値は、Windows レジストリから取得します。 レジストリ設定がない場合は、既定値は 60 秒にします。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 クエリのタイムアウト値は 0 を設定する場合は、タイムアウトは行われません。およびデータベースとの通信が応答を停止します。 この動作は、開発時に便利な可能性があります。 MFC が型の例外をスローする呼び出しが失敗した場合、 [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
 関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
##  <a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected  
 最新の呼び出しによって影響を受けたレコードの数を確認するには、このメンバー関数を呼び出す、 [Execute](#execute)メンバー関数。  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>戻り値  
 影響を受けたレコード数を表す長整数。  
  
### <a name="remarks"></a>コメント  
 返される値には、削除、更新、またはを使用して実行アクション クエリによって挿入されたレコードの数が含まれています。 **Execute**します。 返されるカウントを重ねて表示を更新または削除時に関連付けられたテーブル内の変更が反映反映されません。  
  
 関連情報については、DAO ヘルプの「RecordsAffected プロパティ」を参照してください。  
  
##  <a name="getrelationcount"></a>CDaoDatabase::GetRelationCount  
 このメンバー関数を呼び出して、データベース内のテーブル間で定義されているリレーションシップの数を取得します。  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベース内のテーブル間で定義されているリレーションシップの数。  
  
### <a name="remarks"></a>コメント  
 **GetRelationCount**データベースの関係のコレクションに定義されているすべての関係をループする必要がある場合に便利です。 コレクション内の指定された関係に関する情報を取得するには、次を参照してください。 [GetRelationInfo](#getrelationinfo)します。  
  
 リレーションシップの概念を示すためには、仕入先のテーブルと一対多のリレーションシップがある Products テーブルを検討してください。 このリレーションシップでは、1 つの仕入先は複数の製品を提供できます。 ほかの関係は、一対一および多対多です。  
  
##  <a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo  
 このメンバー関数を呼び出してデータベースの関係のコレクションに指定されたリレーションシップに関する情報を取得します。  
  
```  
void GetRelationInfo(
    int nIndex,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetRelationInfo(
    LPCTSTR lpszName,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、データベースの関係のコレクションでのリレーションシップ オブジェクトのインデックス。  
  
 *relinfo*  
 参照、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)必要な情報を表すオブジェクト。  
  
 `dwInfoOptions`  
 取得する関係に関する情報を指定するオプションです。 使用可能なオプションは、どのようなにより、関数が返す情報もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、テーブルの外部テーブル  
  
- `AFX_DAO_SECONDARY_INFO`属性、フィールドの情報  
  
 フィールドの情報は、 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)リレーションシップに関係する主テーブルからフィールドを含むオブジェクト。  
  
 `lpszName`  
 Relation オブジェクトの名前で検索する場合の名前を表す文字列。  
  
### <a name="remarks"></a>コメント  
 この関数の&2; つのバージョンは、インデックスまたは名前のいずれかのアクセスを提供します。 返される情報の詳細については*relinfo*を参照してください、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求した場合も、以前のレベルにある情報を取得します。  
  
> [!NOTE]
>  リレーションシップの連鎖操作をアクティブ化するオブジェクトの属性を設定した場合 ( **dbRelationUpdateCascades**または**dbRelationDeleteCascades**) が変更されたときに、複数の他のテーブルに関連する主キー テーブル、または Microsoft Jet データベース エンジンを自動的に更新または&1; つのレコードを削除します。 たとえば、Customers テーブルと Orders テーブルの間で連鎖削除のリレーションシップを確立するとします。 Customers テーブルからレコードを削除すると、その顧客に関連する Orders テーブル内のレコードも削除されます。 さらに、連鎖削除の Orders テーブルとその他のテーブル間のリレーションシップを確立すると、これらのテーブルからレコードは自動的に削除 Customers テーブルからレコードを削除します。  
  
##  <a name="gettabledefcount"></a>CDaoDatabase::GetTableDefCount  
 このメンバー関数を呼び出して、データベースで定義されているテーブルの数を取得します。  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>戻り値  
 データベースで定義されているテーブル定義の数。  
  
### <a name="remarks"></a>コメント  
 `GetTableDefCount`データベースのテーブル定義のコレクション内のすべてのテーブルをループする必要がある場合に役立ちます。 コレクション内の特定のテーブルに関する情報を取得するには、次を参照してください。[プライマリ](#gettabledefinfo)します。  
  
##  <a name="gettabledefinfo"></a>Cdaodatabase::gettabledefinfo  
 各種のデータベースで定義されているテーブルに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetTableDefInfo(
    int nIndex,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetTableDefInfo(
    LPCTSTR lpszName,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、データベースのテーブル定義コレクション内のテーブル定義オブジェクトのインデックス。  
  
 `tabledefinfo`  
 参照、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)オブジェクトを必要な情報を返します。  
  
 `dwInfoOptions`  
 取得するテーブルに関する情報を指定するオプションです。 使用可能なオプションは、どのようなにより、関数が返す情報もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)更新可能な名、属性  
  
- `AFX_DAO_SECONDARY_INFO`プライマリ情報に加えて: 作成日付、最終更新日、ソース テーブル名、接続  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報に加えて: 検証規則、検証のテキスト レコード カウント  
  
 `lpszName`  
 名前で検索する場合、テーブル定義オブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 関数の&2; つのバージョンは、テーブルを選択するには、データベースのテーブル定義のコレクション内のインデックスまたはテーブルの名前のいずれかのように提供されます。  
  
 返される情報の詳細については`tabledefinfo`を参照してください、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求した場合は、そのレベルもの情報を取得します。  
  
> [!NOTE]
>  `AFX_DAO_ALL_INFO`オプションの取得に時間がかかることができる情報が提供されます。 ここでは、テーブル内のレコードのカウントは非常に時間がかかる場合は、多くのレコードができます。  
  
##  <a name="getversion"></a>CDaoDatabase::GetVersion  
 Microsoft Jet データベース ファイルのバージョンを確認するには、このメンバー関数を呼び出します。  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース ファイルのバージョンを示します。  
  
### <a name="remarks"></a>コメント  
 返される値が"major.minor"; の形式でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。 日付にバージョンは 1.0、1.1、2.0 および 3.0 です。  
  
 関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。  
  
##  <a name="isopen"></a>CDaoDatabase::IsOpen  
 判断するには、このメンバー関数を呼び出すかどうか、`CDaoDatabase`オブジェクトがデータベースで現在開かれています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDaoDatabase`オブジェクトが現在開いている。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdaodatabase"></a>CDaoDatabase::m_pDAODatabase  
 DAO データベース オブジェクトの基になるは、OLE インターフェイスへのポインターを含む、`CDaoDatabase`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
 DAO の呼び出し元に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
##  <a name="m_pworkspace"></a>CDaoDatabase::m_pWorkspace  
 ポインターを含む、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)データベース オブジェクトを格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ワークスペースに直接アクセスする必要がある場合は、このポインターを使用して、たとえば、ワークスペースのデータベース コレクション内で他のデータベース オブジェクトへのポインターを取得するためです。  
  
##  <a name="open"></a>CDaoDatabase::Open  
 新しく構築を初期化するには、このメンバー関数を呼び出す必要があります`CDaoDatabase`を既存のデータベースを表すオブジェクト。  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存の Microsoft Jet の名前を指定する文字列式 (します。MDB) データベース ファイルです。 ファイル名に拡張子がある場合が必要です。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合も指定できます、ネットワーク パスなど、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"です。 (ために、文字列リテラルで二重の円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
 使用時に、いくつかの考慮事項が適用`lpszName`します。 場合にします。  
  
-   既に別のユーザー型の例外がスローされる MFC によって排他アクセスで開かれているデータベースを指す[CDaoException](../../mfc/reference/cdaoexception-class.md)します。 例外をトラップすることで、ユーザー、データベースが使用できないことを確認します。  
  
-   空の文字列 ("") と*lpszConnect* "ODBC;"では、ユーザーがデータベースを選択できるように、登録されているすべての ODBC データ ソース名の一覧を表示する ダイアログ ボックスが表示されます。 ODBC データ ソースへの直接接続を避ける必要があります。代わりに接続されているテーブルを使用します。  
  
-   それ以外の場合は、既存のデータベースまたは有効な ODBC データ ソース名、MFC がスローされる例外の種類を参照しない`CDaoException`します。  
  
> [!NOTE]
>  詳細については、DAO のエラー コードは、DAOERR を参照してください。H ファイルです。 関連情報については、「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 `bExclusive`  
 ブール値**TRUE**かどうか、データベースは (非共有) への排他アクセス用に開かれると**FALSE**データベースが共有アクセス用に開かれる場合。 この引数を省略すると、共有アクセスでデータベースを開きます。  
  
 `bReadOnly`  
 ブール値**TRUE**かどうか、データベースは読み取り専用アクセス用に開かれると**FALSE**データベースが読み取り/書き込みアクセス用に開かれる場合。 この引数を省略した場合、データベースは読み取り/書き込みアクセスで開かします。 従属するすべてのレコード セットは、この属性を継承します。  
  
 `lpszConnect`  
 データベースを開くに使用する文字列式です。 この文字列の構成、ODBC 接続の引数。 ソース文字列を指定して排他的読み取り専用の引数を指定する必要があります。 データベースが Jet データベースの場合 (します。MDB)、この文字列が空 ("") です。 既定値の構文: **_T**(""): アプリケーションのビルド時に ANSI と Unicode の移植性を提供します。  
  
### <a name="remarks"></a>コメント  
 **開いている**を基になる DAO オブジェクト、データベースに関連付けます。 初期化されるまで、レコード セットや定義されているオブジェクトがクエリ定義を作成するのにデータベース オブジェクトを使用することはできません。 **開いている**データベース オブジェクトを関連付けられているワークスペースのデータベース コレクションに追加します。  
  
 ようパラメーターを使用します。  
  
-   Microsoft Jet を開いている場合は (します。MDB) データベースを使用して、`lpszName`パラメーターを渡しますが、空の文字列が、`lpszConnect`形式のパスワード文字列を渡すか、パラメーター";PWD = パスワード"データベースがパスワードで保護されている場合 (します。MDB データベースの場合のみ)。  
  
-   ODBC データ ソースを開く場合に有効な ODBC 接続文字列を渡す`lpszConnect`を空の文字列で`lpszName`します。  
  
 関連情報については、DAO ヘルプの「OpenDatabase メソッド」を参照してください。  
  
> [!NOTE]
>  外部データベース、ISAM データベースなど、ODBC データ ソースにアクセスするときのパフォーマンスの向上のためお勧め外部データベース テーブルは、Microsoft Jet エンジン データベースに接続する (。MDB) データ ソースに直接接続するのではなく。  
  
 たとえば、DBMS ホストが使用できない場合は、接続試行がタイムアウトする可能性です。 接続の試行が失敗した場合、**開く**型の例外をスロー [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
 残りの「解説」は、ODBC データベースだけに適用されます。  
  
 かどうか、データベースは、ODBC データベースとでは、パラメーター、**開く**呼び出しが接続するために十分な情報を含まない、ODBC ドライバーは、ユーザーから必要な情報を取得するダイアログ ボックスを開きます。 呼び出すと**開く**、接続文字列、`lpszConnect`非公開で格納され、呼び出すことによって利用可能な[GetConnect](#getconnect)メンバー関数。  
  
 呼び出す前に、独自のダイアログ ボックスを開く場合は、**を開く**パスワードなどのユーザーから情報を取得し、その情報、接続文字列を追加に渡す**開く**します。 時間を短縮できる再利用できるように、次に (おそらく、Windows レジストリに) 指定した接続文字列にアプリケーション呼び出しことができますか**開く**上、`CDaoDatabase`オブジェクトです。  
  
 ログイン承認の複数レベルの接続文字列を使用することもできます (それぞれ異なるを`CDaoDatabase`オブジェクト) またはその他のデータベースに固有の情報を伝達します。  
  
##  <a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout  
 後続の処理を接続されているデータベースのタイムアウトになるまでの秒数の既定をオーバーライドする場合は、このメンバー関数を呼び出します。  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSeconds`  
 タイムアウトするクエリの試行までの秒数。  
  
### <a name="remarks"></a>コメント  
 操作は、ネットワーク アクセスの問題や、過剰なクエリの処理時間のためタイムアウト可能性があります。 呼び出す`SetQueryTimeout`またはレコード セットの前に、レコード セットを開く前に[AddNew](../../mfc/reference/cdaorecordset-class.md#addnew)、[更新](../../mfc/reference/cdaorecordset-class.md#update)、または[削除](../../mfc/reference/cdaorecordset-class.md#delete)メンバー関数をクエリのタイムアウト値を変更する場合。 後続のすべての設定に影響[開く](../../mfc/reference/cdaorecordset-class.md#open)、 `AddNew`、**更新**と**削除**これに関連付けられているすべてのレコード セットへの呼び出し`CDaoDatabase`オブジェクトです。 開いた後、レコード セットのクエリ タイムアウト値を変更しても、レコード セットの値は変わりません。 例については、その後[移動](../../mfc/reference/cdaorecordset-class.md#move)操作は、新しい値を使用しないでください。  
  
 クエリ タイムアウトの既定値は、60 秒です。 すべてのデータベースでは、クエリのタイムアウト値を設定する機能をサポートします。 クエリのタイムアウト値は 0 を設定する場合は、タイムアウトは行われません。データベースとの通信が応答を停止します。 この動作は、開発時に便利な可能性があります。  
  
 関連情報については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)

