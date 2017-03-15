---
title: "CDaoWorkspace クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoWorkspace
dev_langs:
- C++
helpviewer_keywords:
- DAO workspaces [C++]
- transaction spaces [C++], DAO workspace
- ODBC classes [C++], vs. DAO classes
- default workspaces [C++], DAO
- workspaces [C++], DAO
- sessions [C++], DAO workspace
- Workspace class
- CDaoWorkspace class
- workspaces [C++], interface to database engine
- Workspaces collection
- persistence [C++], DAO workspace
- workspaces [C++], default
- defaults [C++], workspaces
- DAO workspaces [C++], CDaoWorkspace class
- security [MFC], DAO workspaces
- security [MFC]
- database engine [C++], accessing via workspace
- transaction spaces [C++]
- DDLs [C++]
- workspaces [C++], persistence
- default workspaces [C++]
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
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
ms.openlocfilehash: 5d7f9aea6fa4913641bc92662b3cf5dfeaddb9d8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace クラス
シングル ユーザーによる名前付きの、パスワードで保護されたデータベース セッションのログインからログオフまでを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Workspace オブジェクトを構築します。 その後を呼び出す**作成**または**開く**します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|データベース エンジンのワークスペースのコレクションを新しく作成したワークスペースを追加します。|  
|[CDaoWorkspace::BeginTrans](#begintrans)|ワークスペースのすべての開いているデータベースに適用される新しいトランザクションを開始します。|  
|[CDaoWorkspace::Close](#close)|ワークスペースおよびすべての含まれているオブジェクトを閉じます。 保留中のトランザクションがロールバックされます。|  
|[CDaoWorkspace::CommitTrans](#committrans)|現在のトランザクションを完了し、変更を保存します。|  
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|データベースを圧縮 (または複製) します。|  
|[CDaoWorkspace::Create](#create)|新しい DAO workspace オブジェクトを作成します。|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|ワークスペースのデータベース コレクション内には、DAO データベース オブジェクトの数を返します。|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|ワークスペースのデータベース コレクション内で定義されている、指定した DAO データベースに関する情報を返します。|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を返します。|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|データ ソースへの接続を適用して、同じ ODBC データ ソースに関連する複数のトランザクションが個別にされているかどうかを示す値を返します。|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|ユーザーが ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を返します。|  
|[CDaoWorkspace::GetName](#getname)|Workspace オブジェクトのユーザー定義名を返します。|  
|[CDaoWorkspace::GetUserName](#getusername)|ワークスペースの作成時にユーザー名の指定を返します。 これは、ワークスペースの所有者の名前です。|  
|[CDaoWorkspace::GetVersion](#getversion)|ワークスペースに関連付けられているデータベース エンジンのバージョンを含む文字列を返します。|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|データベース エンジンのワークスペースのコレクション内には、ワークスペースの DAO オブジェクトの数を返します。|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|データベース エンジンの Workspaces コレクションで定義されている指定された DAO ワークスペースについての情報を返します。|  
|[CDaoWorkspace::Idle](#idle)|により、データベース エンジンは、バック グラウンド タスクを実行します。|  
|[CDaoWorkspace::IsOpen](#isopen)|ワークスペースがある場合は&0; 以外を返しますが開きます。|  
|[ので、使用できません。](#open)|DAO の既定のワークスペースに関連付けられている workspace オブジェクトを明示的に開きます。|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|破損したデータベースの修復を試みます。|  
|[CDaoWorkspace::Rollback](#rollback)|現在のトランザクションを終了し、変更を保存できません。|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|パスワードを指定せずにワークスペースを作成するときに、データベース エンジンが使用するパスワードを設定します。|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用するユーザー名を設定します。|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を設定します。|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|データ ソースへの接続を強制することで、同じ ODBC データ ソースに関連する複数のトランザクションを分離するかどうかを指定します。|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|ユーザーが ODBC データ ソースにログインしようとしたときにエラーが発生するまでの秒数を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|基になる DAO workspace オブジェクトへのポインター。|  
  
## <a name="remarks"></a>コメント  
 ほとんどの場合、複数のワークスペースが不要し、明示的にワークスペース オブジェクトを作成する必要はありません。データベースとレコード セット オブジェクトを開くと、DAO の既定のワークスペースを使用します。 ただし、必要な場合、追加の作業領域オブジェクトを作成することで複数のセッション同時に実行できます。 各ワークスペースのオブジェクトには、独自のデータベース コレクション内で複数のオープンなデータベース オブジェクトを含めることができます。 MFC では、ワークスペースとは、主に、トランザクション マネージャーは、「トランザクション空間」同じ、開いているデータベースのセットを指定します。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前には、"CDao"プレフィックスがあります。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて MFC クラスよりもより高機能なです。 DAO ベースのクラスの ODBC ドライバーを含む Microsoft Jet データベース エンジンを介してデータにアクセスします。 データベースを作成して、DAO を直接呼び出すことがなくテーブルと、クラスを使用してフィールドを追加するなどのデータ定義言語 (DDL) 操作もサポートします。  
  
## <a name="capabilities"></a>機能  
 クラス`CDaoWorkspace`次を提供します。  
  
-   データベース エンジンを初期化することによって作成された既定のワークスペースに必要な場合は、明示的なアクセスします。 通常、使用する DAO の既定のワークスペースに暗黙的にデータベースとレコード セット オブジェクトを作成します。  
  
-   トランザクションがすべてのデータベースに適用されるトランザクションの領域は、ワークスペースで開きます。 別のトランザクション空間を管理するその他のワークスペースを作成できます。  
  
-   基になる Microsoft Jet データベース エンジンの多くのプロパティへのインターフェイス (静的メンバー関数を参照してください)。 開くまたは、ワークスペースを作成する前に静的メンバー関数の呼び出しを開くまたは作成、データベース エンジンを初期化します。  
  
-   それに追加されたすべてのアクティブなワークスペースを格納するデータベース エンジンの Workspaces コレクションにアクセスします。 作成し、コレクションに追加せずにワークスペースを使用することもできます。  
  
## <a name="security"></a>セキュリティ  
 MFC は、セキュリティの制御に使用される DAO でのユーザーとグループのコレクションを実装していません。 これらの側面を DAO の場合は、必要がありますプログラミングを行うに自分で DAO インターフェイスへの直接呼び出しを使用しています。 詳細については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
## <a name="usage"></a>使用方法  
 クラスを使用して`CDaoWorkspace`にします。  
  
-   明示的に既定のワークスペースを開きます。  
  
     通常、既定のワークスペースは、暗黙的な-新しいが開く[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトです。 明示的にアクセスする必要がありますが、-などを access データベース エンジンのプロパティまたは Workspaces コレクションです。 「既定のワークスペースの暗黙的な使用」を参照してください。  
  
-   新しいワークスペースを作成します。 呼び出す[Append](#append) Workspaces コレクションに追加する場合。  
  
-   Workspaces コレクションでは、既存のワークスペースを開きます。  
  
 新しいワークスペースを作成する存在しないコレクションが下に記載されているワークスペースで、[作成](#create)メンバー関数。 ワークスペースのオブジェクトは、データベースの例のエンジン セッション間で任意の方法では保持されません。 アプリケーションが MFC を静的にリンクしている場合は、データベース エンジン非初期化アプリケーションが終了します。 アプリケーションは、MFC と動的にリンク、している場合、データベース エンジンが MFC DLL を読み込むときと初期化されていません。  
  
 明示的に既定のワークスペースを開くか、Workspaces コレクションで開いて、既存のワークスペースは」の説明、[開く](#open)メンバー関数。  
  
 ワークスペースを閉じて、ワークスペースのセッションを終了、[閉じる](#close)メンバー関数。 **閉じる**が閉じられていない、コミットされていないトランザクションをロールバックするすべてのデータベースを閉じます。  
  
## <a name="transactions"></a>トランザクション  
 DAO は、ワークスペース レベルでトランザクションを管理します。そのため、複数の開いているデータベースとワークスペースでのトランザクションは、すべてのデータベースに適用されます。 などの場合は&2; つのデータベースがコミットされていない更新プログラムを呼び出す[CommitTrans](#committrans)、すべての更新はコミットされます。 単一のデータベースにトランザクションを制限する場合はその別のワークスペース オブジェクトする必要があります。  
  
## <a name="implicit-use-of-the-default-workspace"></a>既定のワークスペースは、暗黙的に使用します。  
 MFC では、次の状況で暗黙的に DAO の既定のワークスペースを使用します。  
  
-   新規に作成する場合`CDaoDatabase`オブジェクトが、これを既存を通じて`CDaoWorkspace`MFC 一時ワークスペース オブジェクトを作成するには、DAO の既定のワークスペースに対応するオブジェクトします。 既定のワークスペースに関連付けられているは、複数のデータベースのすべてのデータベース オブジェクトを作成する場合。 使って、データベースのワークスペースにアクセスすることができます、`CDaoDatabase`データ メンバーです。  
  
-   同様を作成する場合、`CDaoRecordset`オブジェクトへのポインターを指定せず、`CDaoDatabase`オブジェクト、MFC は、一時的なデータベース オブジェクトを作成および拡張機能により、一時的なワークスペースのオブジェクト。 レコード セットのデータベース、および間接的に、ワークスペースをを通じてアクセスできる、`CDaoRecordset`データ メンバーです。  
  
## <a name="other-operations"></a>その他の操作  
 データベースの破損を修復またはデータベースの最適化など、他のデータベース操作も提供します。  
  
 DAO のセキュリティと直接に DAO を呼び出す方法の詳細について、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="a-nameappenda--cdaoworkspaceappend"></a><a name="append"></a>CDaoWorkspace::Append  
 呼び出した後に、このメンバー関数を呼び出して[作成](#create)します。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 **追加**新しく作成したワークスペースのオブジェクトをデータベース エンジンの Workspaces コレクションに追加します。 ワークスペースは、データベース エンジンのセッションの間は保持されません。ディスクではなく、メモリ内にのみ保存されます。 ワークスペースを追加する必要はありません。そうしない場合は、引き続き使用できます。  
  
 追加されたワークスペースは、アクティブなワークスペースのコレクションで開いている状態が呼び出されるまでその[閉じる](#close)メンバー関数。  
  
 関連情報については、DAO ヘルプの「メソッドの追加」を参照してください。  
  
##  <a name="a-namebegintransa--cdaoworkspacebegintrans"></a><a name="begintrans"></a>CDaoWorkspace::BeginTrans  
 このメンバー関数を呼び出してトランザクションを開始します。  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後**BeginTrans**トランザクションをコミットすると、データまたはデータベースの構造に行った更新が有効になります。 ワークスペースは、単一のトランザクション領域を定義するため、トランザクションは、ワークスペース内のすべての開いているデータベースに適用されます。 トランザクションを完了する&2; つの方法があります。  
  
-   呼び出す、 [CommitTrans](#committrans)メンバー関数をトランザクションをコミットし、データ ソースに変更を保存します。  
  
-   呼び出すか、[ロールバック](#rollback)トランザクションをキャンセルするメンバー関数。  
  
 Workspace オブジェクトまたはデータベース オブジェクトを閉じて、トランザクションが保留中の間は、保留中のすべてのトランザクションはロールバックします。  
  
 1 つの ODBC データ ソースから別の ODBC データ ソース上でのトランザクションを分離する必要がある場合を参照してください、 [SetIsolateODBCTrans](#setisolateodbctrans)メンバー関数。  
  
##  <a name="a-namecdaoworkspacea--cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a>CDaoWorkspace::CDaoWorkspace  
 `CDaoWorkspace` オブジェクトを構築します。  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>コメント  
 C++ オブジェクトを構築した後に、2 つのオプションがあります。  
  
-   オブジェクトの[開く](#open)メンバー関数を既定のワークスペースを開くまたは Workspaces コレクションの既存のオブジェクトを開きます。  
  
-   オブジェクトのまたは[作成](#create)新しい DAO workspace オブジェクトを作成します。 これは、明示的に新しいワークスペースはセッションを開始を使用して参照することができる`CDaoWorkspace`オブジェクトです。 呼び出した後**作成**、呼び出すことができます[Append](#append)ワークスペースをデータベース エンジンの Workspaces コレクションに追加する場合。  
  
 クラスの概要を参照してください[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)について明示的に作成する必要がある場合は、`CDaoWorkspace`オブジェクトです。 通常は、開くときに暗黙的に作成したワークスペースを使用、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト ワークスペースを指定せず、または開くとき、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)データベース オブジェクトを指定することがなくオブジェクトです。 この方法で作成した MFC DAO オブジェクトは、1 回だけ作成され、再利用 DAO の既定のワークスペースを使用します。  
  
 ワークスペースと内にあるオブジェクトを解放する呼び出し workspace オブジェクトの[閉じる](#close)メンバー関数。  
  
##  <a name="a-nameclosea--cdaoworkspaceclose"></a><a name="close"></a>CDaoWorkspace::Close  
 ワークスペースのオブジェクトをクローズする場合は、このメンバー関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 ワークスペースを開くオブジェクトを閉じるは基になる DAO オブジェクトを解放し、ワークスペースが Workspaces コレクションのメンバーである場合は、コレクションから削除します。 呼び出す**閉じる**お勧めします。  
  
> [!CAUTION]
>  Workspace オブジェクトを閉じると、ワークスペースに開かれているデータベースが実行されます。 これは、結果、レコード セット開いても、終了して、データベース内でされ、すべての保留中の変更や更新がロールバックします。 関連情報については、次を参照してください。、 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close)、 [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close)、 [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close)、および[CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close)メンバー関数。  
  
 ワークスペースのオブジェクトは恒久的です。それらへの参照が存在している間にのみ存在します。 これは、あるデータベース エンジンのセッションの終了時に、ワークスペースとそのデータベースのコレクションは保持されないことを意味します。 必要があります再作成するには次のセッションをワークスペースとデータベースをもう一度開いています。  
  
 関連情報については、DAO ヘルプの「閉じるメソッド」を参照してください。  
  
##  <a name="a-namecommittransa--cdaoworkspacecommittrans"></a><a name="committrans"></a>CDaoWorkspace::CommitTrans  
 トランザクションをコミットするには、このメンバー関数を呼び出すの編集と更新プログラム グループをワークスペースで、1 つまたは複数のデータベースに保存します。  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>コメント  
 トランザクションでは、一連のデータベース内のデータまたはデータへの呼び出しで始まる、構造体への変更の[BeginTrans](#begintrans)します。 トランザクションを完了したときにコミットするかロールバック (変更の取り消し) と[ロールバック](#rollback)します。 既定では、トランザクションを使用しない更新レコードをすぐにコミットされます。 呼び出す**BeginTrans**によりが呼び出されるまでに遅延する更新プログラムのコミットメント**CommitTrans**します。  
  
> [!CAUTION]
>  1 つのワークスペース内では、トランザクションは常に、ワークスペースにグローバルと、データベースまたはレコード セットの&1; つだけに限定されません。 1 つ以上のデータベースやワークスペースのトランザクション内でレコード セットに対する操作を実行する場合**CommitTrans**更新、保留中のすべてのコミットおよび**ロールバック**データベースとレコード セットのすべての操作を復元します。  
  
 データベースまたは保留中のトランザクションでワークスペースを閉じると、トランザクションはすべてロールバックされます。  
  
> [!NOTE]
>  これは、2 フェーズ コミットのメカニズムではありません。 1 つの更新は、コミットに失敗した場合、他のユーザーもコミットされます。  
  
##  <a name="a-namecompactdatabasea--cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a>CDaoWorkspace::CompactDatabase  
 指定した Microsoft Jet を圧縮するには、このメンバー関数を呼び出します (します。MDB) データベース。  
  
```  
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int nOptions = 0);

 
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale,  
    int nOptions,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszSrcName`  
 既存の名前には、データベースが閉じられます。 できますの完全なパスとファイル名など、"c:\\\MYDB します。MDB"です。 ファイル名に拡張子がある場合を指定する必要があります。 ネットワークでは、統一された名前付け規則 (UNC) をサポートする場合も指定できます、ネットワーク パスなど、"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"です。 (ために、パス文字列に円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
 `lpszDestName`  
 作成している最適化されたデータベースの完全パス。 としてネットワーク パスを指定することも`lpszSrcName`です。 使用することはできません、`lpszDestName`と同じデータベース ファイルを指定する引数`lpszSrcName`します。  
  
 `lpszPassword`  
 パスワードで保護されたデータベースを縮小する場合に使用されるパスワードです。 バージョンを使用する場合は、`CompactDatabase`パスワードを取得する、すべてのパラメーターを指定する必要があります。 また、接続パラメーターであるために必要に特殊な書式設定、次のように: です。PWD= `lpszPassword`. 例: です。PWD =「不満」です。 (先頭のセミコロンは、必要です)。  
  
 `lpszLocale`  
 作成するための照合順序を指定するための文字列式`lpszDestName`します。 既定値を受け入れることによって、この引数を省略したかどうかは**dbLangGeneral** (下記参照)、新しいデータベースのロケールとは、元のデータベースと同じです。 指定できる値は次のとおりです。  
  
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
  
 `nOptions`  
 対象のデータベースに対して&1; つまたは複数のオプションを示す`lpszDestName`します。 既定値を受け入れることによってこの引数を省略した場合、`lpszDestName`同じ暗号化とバージョンと同じになります`lpszSrcName`します。 組み合わせることができます、 **dbEncrypt**または**dbDecrypt**でビットごとの OR 演算子を使用するバージョンのオプションのいずれかのオプションです。 データベースの形式でない、データベース エンジンのバージョンを指定できる値は次のとおりです。  
  
- **dbEncrypt**最適化中にデータベースを暗号化します。  
  
- **dbDecrypt**最適化中に、データベースの暗号化を解除します。  
  
- **dbVersion10**最適化中に Microsoft Jet データベース エンジンのバージョン 1.0 を使用するデータベースを作成します。  
  
- **dbVersion11**最適化中に Microsoft Jet データベース エンジンのバージョン 1.1 を使用するデータベースを作成します。  
  
- **dbVersion20**最適化中に Microsoft Jet データベース エンジンのバージョン 2.0 を使用するデータベースを作成します。  
  
- **dbVersion30**最適化中に Microsoft Jet データベース エンジンのバージョン 3.0 を使用するデータベースを作成します。  
  
 使用することができます**dbEncrypt**または**dbDecrypt**オプションの引数に暗号化するかは圧縮に応じて、データベースの暗号化を解除するかを指定します。 暗号化定数を省略した場合、または両方を含めた場合**dbDecrypt**と**dbEncrypt**、`lpszDestName`と同じ暗号化が`lpszSrcName`です。 バージョンのいずれかの操作は、最適化されたデータベースのデータ形式のバージョンを指定するのにオプションの引数で使用できます。 この定数のデータ形式のバージョンのみに影響を与えます`lpszDestName`します。 1 つだけのバージョンの定数を指定できます。 バージョンの定数を省略した場合`lpszDestName`と同じバージョンを持つ`lpszSrcName`です。 圧縮できる`lpszDestName`が同じではバージョンにのみまたはこれ以降の場合よりも`lpszSrcName`です。  
  
> [!CAUTION]
>  データベースが暗号化されていない場合、可能な場合でもあるデータベースを構成するバイナリ ディスク ファイルを直接読み取るユーザー/パスワード セキュリティを実装します。  
  
### <a name="remarks"></a>コメント  
 データベース内のデータを変更すると、データベース ファイル断片化されて、必要に応じてより多くのディスク領域を使用します。 定期的に、データベース ファイルを最適化するデータベースを最適化する必要があります。 最適化されたデータベースは、通常小さくなります。 コピーし、データベースを縮小する間に、照合順序、暗号化、またはデータ形式のバージョンを変更することもできます。  
  
> [!CAUTION]
>  `CompactDatabase`メンバー関数は正しく完全な Microsoft Access データベース&1; つのバージョンから別に変換しません。 データ形式のみが変換されます。 フォームやレポートなど、Microsoft のアクセスは定義オブジェクトは変換されません。 ただし、データは正しく変換されます。  
  
> [!TIP]
>  使用することも`CompactDatabase`データベース ファイルをコピーします。  
  
 データベース圧縮に関する詳細については、DAO ヘルプの「CompactDatabase メソッド」を参照してください。  
  
##  <a name="a-namecreatea--cdaoworkspacecreate"></a><a name="create"></a>CDaoWorkspace::Create  
 このメンバー関数を呼び出して新しい DAO workspace オブジェクトを作成し、MFC に関連付けます`CDaoWorkspace`オブジェクトです。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 新しい workspace オブジェクトの一意名を最大 14 文字の文字列。 名を指定する必要があります。 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *lpszUserName*  
 ワークスペースの所有者のユーザー名。 要件については、次を参照してください。、`lpszDefaultUser`パラメーターを、 [SetDefaultUser](#setdefaultuser)メンバー関数。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
 `lpszPassword`  
 新しい workspace オブジェクトのパスワードです。 パスワードは、長さは最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは、大文字小文字が区別されます。 関連情報については、DAO ヘルプの「パスワード プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 全体的な作成手順に示します。  
  
1.  構築、 [CDaoWorkspace](#cdaoworkspace)オブジェクトです。  
  
2.  オブジェクトの**作成**メンバー関数を基になる DAO ワークスペースを作成します。 ワークスペース名を指定する必要があります。  
  
3.  必要に応じて呼び出す[Append](#append)ワークスペースをデータベース エンジンの Workspaces コレクションに追加する場合。 追加することがなく、ワークスペースを使用することができます。  
  
 後に、**作成**呼び出し、workspace オブジェクトは、開いている状態で、使用可能な状態にします。 呼び出さない**開く**後**作成**します。 呼び出さない**作成**Workspaces コレクションで、ワークスペースが既に存在する場合。 **作成**は既に初期化されていない場合は、データベース エンジンを初期化します。  
  
##  <a name="a-namegetdatabasecounta--cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount  
 ワークスペースのデータベース コレクション内で DAO データベース オブジェクトの数を取得するには、このメンバー関数を呼び出す-ワークスペースに開かれているデータベースの数。  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>戻り値  
 ワークスペース内の開いているデータベースの数。  
  
### <a name="remarks"></a>コメント  
 `GetDatabaseCount`ワークスペースのデータベース コレクション内で定義されているすべてのデータベースをループする必要がある場合に便利です。 コレクション内の特定のデータベースに関する情報を取得するには、次を参照してください。 [GetDatabaseInfo](#getdatabaseinfo)します。 一般的な使用方法は、呼び出すこと`GetDatabaseCount`で開かれているデータベースの数、番号を使用するループ インデックスとして呼び出しの繰り返しに`GetDatabaseInfo`します。  
  
##  <a name="a-namegetdatabaseinfoa--cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo  
 さまざまな種類のデータベースを開く ワークスペースで情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetDatabaseInfo(
    int nIndex,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetDatabaseInfo(
    LPCTSTR lpszName,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、ワークスペースのデータベース コレクション内でデータベース オブジェクトの&0; から始まるインデックス。  
  
 `dbinfo`  
 参照、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)オブジェクトを必要な情報を返します。  
  
 `dwInfoOptions`  
 取得するデータベースに関する情報を指定するオプションです。 使用可能なオプションは、それらの原因として何を返す関数もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前を更新可能なトランザクション  
  
- `AFX_DAO_SECONDARY_INFO`プライマリ情報に加えて: バージョン、照合順序では、クエリのタイムアウト  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報に加えて: 接続  
  
 `lpszName`  
 名前で検索する場合、データベース オブジェクトの名前。 名前は、最大 14 文字の文字列であり、新しい workspace オブジェクトの一意名です。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、インデックスでデータベースを検索することができます。 その他のバージョンでは、データベースを名前で検索することができます。  
  
 返される情報の詳細については`dbinfo`を参照してください、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、そのレベルもの情報を取得します。  
  
##  <a name="a-namegetinipatha--cdaoworkspacegetinipath"></a><a name="getinipath"></a>CDaoWorkspace::GetIniPath  
 Microsoft Jet データベースの場所に、Windows レジストリにエンジンの初期化の設定を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)レジストリの場所を格納しています。  
  
### <a name="remarks"></a>コメント  
 場所を使用すると、データベース エンジンの設定に関する情報を取得します。 返される情報は、実際には、レジストリのサブキーの名前です。  
  
 関連情報については、"IniPath Property"および「をカスタマイズする Windows レジストリ設定のデータ アクセス」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namegetisolateodbctransa--cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a>CDaoWorkspace::GetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC トランザクションが分離されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 いくつかの状況では、同じ ODBC データベース上に保留中の複数の同時トランザクションが必要があります。 これを行うには、トランザクションごとに独立したワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、この速度が低下するシステムのパフォーマンスに留意してください。 トランザクションの分離が必要ないため、同じユーザーによって開かれた複数のワークスペースのオブジェクトからの ODBC 接続は既定で共有されます。  
  
 Microsoft SQL Server などの一部の ODBC サーバーでは、単一の接続での同時トランザクションは許可されません。 保留中のようなデータベースで同時に複数のトランザクションがある場合に IsolateODBCTrans プロパティを設定**TRUE**を開くとすぐには、各ワークスペースにします。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
 関連情報については、DAO ヘルプの「IsolateODBCTrans プロパティ」を参照してください。  
  
##  <a name="a-namegetlogintimeouta--cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a>CDaoWorkspace::GetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC データベースにログインしようとすると、エラーが発生するまでの秒数。  
  
### <a name="remarks"></a>コメント  
 この値は、ODBC データベースにログインしようとすると、エラーが発生するまでの秒数を表します。 既定の LoginTimeout 設定は、20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果、接続が失敗するが、Microsoft SQL Server などの ODBC データベースにログインしようとするか、サーバーが実行されていないためです。 待機している既定の 20 秒間の接続のではなく、データベース エンジンがエラーを生成するまでに待機する時間を指定できます。 サーバーへログインは、外部サーバーのデータベースに対するクエリの実行など、さまざまなイベントの数値の一部として暗黙的に実行されます。  
  
 関連情報については、DAO ヘルプの「LoginTimeout プロパティ」を参照してください。  
  
##  <a name="a-namegetnamea--cdaoworkspacegetname"></a><a name="getname"></a>CDaoWorkspace::GetName  
 このメンバー関数を呼び出して、ユーザー定義の名前を取得、DAO ワークスペース オブジェクトの基になる、`CDaoWorkspace`オブジェクトです。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO workspace オブジェクトのユーザー定義名を格納します。  
  
### <a name="remarks"></a>コメント  
 名前は、データベース エンジンのワークスペースのコレクションの DAO ワークスペース オブジェクト名でアクセスするのに便利です。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="a-namegetusernamea--cdaoworkspacegetusername"></a><a name="getusername"></a>CDaoWorkspace::GetUserName  
 このメンバー関数を呼び出して、ワークスペースの所有者の名前を取得します。  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) workspace オブジェクトの所有者を表します。  
  
### <a name="remarks"></a>コメント  
 を取得またはワークスペースの所有者のアクセス許可を設定するには、Permissions プロパティの設定を確認するには、直接 DAO を呼び出すアクセス許可を決定するこのユーザーが持ちます。 アクセス許可を使用するには、システムが必要です。MDA ファイルです。  
  
 DAO の呼び出し元に関する情報を参照してください、直接[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
##  <a name="a-namegetversiona--cdaoworkspacegetversion"></a><a name="getversion"></a>CDaoWorkspace::GetVersion  
 使用中の Microsoft Jet データベース エンジンのバージョンを確認するには、このメンバー関数を呼び出します。  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトに関連付けられているデータベース エンジンのバージョンを示します。  
  
### <a name="remarks"></a>コメント  
 返される値が"major.minor"; の形式でバージョン番号を表しますたとえば、「3.0」です。 製品のバージョン番号 (たとえば、3.0) は、バージョン番号 (3)、ピリオド、およびリリース番号 (0) で構成されます。  
  
 関連情報については、DAO ヘルプの「バージョン プロパティ」を参照してください。  
  
##  <a name="a-namegetworkspacecounta--cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a>CDaoWorkspace::GetWorkspaceCount  
 DAO データベース エンジンの Workspaces コレクションでオブジェクトのワークスペースの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>戻り値  
 Workspaces コレクション内の開いているワークスペースの数。  
  
### <a name="remarks"></a>コメント  
 この数は、コレクションに追加されていない、開いているワークスペースには含まれません。 `GetWorkspaceCount`Workspaces コレクションで定義されているすべてのワークスペース内をループする必要がある場合に便利です。 コレクション内の特定のワークスペースに関する情報を取得するには、次を参照してください。 [GetWorkspaceInfo](#getworkspaceinfo)します。 一般的な使用方法は、呼び出すこと`GetWorkspaceCount`で開いているワークスペースの数、番号を使用するループ インデックスとして呼び出しの繰り返しに`GetWorkspaceInfo`します。  
  
##  <a name="a-namegetworkspaceinfoa--cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a>CDaoWorkspace::GetWorkspaceInfo  
 さまざまな種類のセッションで開かれているワークスペースに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetWorkspaceInfo(
    int nIndex,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetWorkspaceInfo(
    LPCTSTR lpszName,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、ワークスペースのコレクション内のデータベース オブジェクトの&0; から始まるインデックス。  
  
 `wkspcinfo`  
 参照、 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)オブジェクトを必要な情報を返します。  
  
 `dwInfoOptions`  
 取得するワークスペースに関する情報を指定するオプションです。 使用可能なオプションは、それらの原因として何を返す関数もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名  
  
- `AFX_DAO_SECONDARY_INFO`プライマリ情報に加えて: ユーザー名  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報に加えて: ODBCTrans の分離  
  
 `lpszName`  
 名前で検索する場合、workspace オブジェクトの名前。 名前は、最大 14 文字の文字列であり、新しい workspace オブジェクトの一意名です。  
  
### <a name="remarks"></a>コメント  
 返される情報の詳細については`wkspcinfo`を参照してください、 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、レベルの情報を取得します。  
  
##  <a name="a-nameidlea--cdaoworkspaceidle"></a><a name="idle"></a>CDaoWorkspace::Idle  
 呼び出す**Idle**が最新でない大量のデータ処理のためのバック グラウンド タスクを実行することによるデータベース エンジンを提供します。  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAction`  
 アイドル状態の処理中に実行するアクション。 現在、唯一の有効なアクションは**dbFreeLocks**します。  
  
### <a name="remarks"></a>コメント  
 多くの場合、これは、マルチ ユーザー、マルチタス キングの環境でもない場合に、レコード セット内のすべてのレコードを最新に保つための十分なバック グラウンドの処理時間に当てはまります。  
  
> [!NOTE]
>  呼び出す**Idle** Microsoft Jet データベース エンジンのバージョン 3.0 で作成されたデータベースでの必要はありません。 使用**Idle**の以前のバージョンで作成されたデータベースだけです。  
  
 通常、読み取りロックを解除し、ローカル ダイナセット タイプの recordset オブジェクト内のデータは、他のアクション (マウスの動きを含む) が実行されていない場合にのみ更新されます。 定期的を呼び出す場合**Idle**、データベース エンジンの時刻にバック グラウンド タスクをリリースすることによって処理の遅延を解消する必要のない読み取りロックを提供します。 指定する、 **dbFreeLocks**を引数として定数は、すべての読み取りロックが解除されるまでの処理を遅延します。  
  
 このメンバー関数は、アプリケーションの複数のインスタンスを実行している場合を除き、シングル ユーザー環境では必要ありません。 **Idle**メンバー関数は、データベース エンジンはデータをメモリにロックが解除され、ディスクにフラッシュを強制するため、マルチ ユーザー環境でパフォーマンスが向上します。 読み取りロックを解放するには、トランザクションの操作のパーツを作成します。  
  
 関連情報については、DAO ヘルプの「メソッドの待機中の」を参照してください。  
  
##  <a name="a-nameisopena--cdaoworkspaceisopen"></a><a name="isopen"></a>CDaoWorkspace::IsOpen  
 判断するには、このメンバー関数を呼び出すかどうか、`CDaoWorkspace`オブジェクトが開いて-つまりかどうか、MFC オブジェクトが初期化されてへの呼び出しによって[開く](#open)やへの呼び出し[作成](#create)します。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Workspace オブジェクトが開いている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数を呼び出すこと、メンバーのいずれかのワークスペースを開いている状態にします。  
  
##  <a name="a-namempdaoworkspacea--cdaoworkspacempdaoworkspace"></a><a name="m_pdaoworkspace"></a>CDaoWorkspace::m_pDAOWorkspace  
 基になる DAO workspace オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 基になる DAO オブジェクトへのアクセスを指示する必要がある場合は、このデータ メンバーを使用します。 このポインターを通じて、DAO オブジェクトのインターフェイスを呼び出すことができます。  
  
 DAO オブジェクトに直接アクセスする方法については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
##  <a name="a-nameopena--cdaoworkspaceopen"></a><a name="open"></a>ので、使用できません。  
 DAO の既定のワークスペースに関連付けられている workspace オブジェクトを明示的に開きます。  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 オブジェクトの名前、DAO ワークスペースを開くには、ワークスペースの一意名を最大 14 文字の文字列です。 既定値をそのまま**NULL**を明示的に既定のワークスペースを開きます。 名前付けに関する要件を参照してください、`lpszName`パラメーター[作成](#create)します。 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 構築した後、`CDaoWorkspace`オブジェクトでこのメンバー関数を呼び出して、次のいずれかの操作を行います。  
  
-   明示的に既定のワークスペースを開きます。 Pass **NULL** for `lpszName`.  
  
-   既存の開く`CDaoWorkspace`オブジェクトの名前によって、ワークスペースのコレクションのメンバーです。 既存のワークスペース オブジェクトの有効な名前を渡します。  
  
 **開く**は workspace オブジェクトを開いている状態にしても、アプリケーションの既に初期化されていない場合、データベース エンジンを初期化します。  
  
 ただし多く`CDaoWorkspace`メンバー関数は、ワークスペースを開いた後にのみ呼び出すことができる、データベース エンジンに対する操作には、次のメンバー関数は使用可能な構造を呼び出す前に、C++ オブジェクトの後に**開く**:  
  
||||  
|-|-|-|  
|[作成します。](#create)|[バージョンの取得](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[アイドル状態します。](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="a-namerepairdatabasea--cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a>CDaoWorkspace::RepairDatabase  
 Microsoft Jet データベース エンジンにアクセスする破損したデータベースを修復しようとする必要がある場合は、このメンバー関数を呼び出します。  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 パスとファイル名、既存の Microsoft Jet エンジンのデータベースのファイルを実行します。 パスを省略した場合は、現在のディレクトリのみが検索されます。 システムでは、統一された名前付け規則 (UNC) をサポートする場合も指定できます、ネットワーク パスなど:"\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB します。MDB"です。 (ために、パス文字列に円記号が必要な"\\"は C++ のエスケープ文字です)。  
  
### <a name="remarks"></a>コメント  
 指定されたデータベースを閉じる必要があります`lpszName`修復する前にします。 マルチ ユーザー環境の場合は、他のユーザーが持つことはできません`lpszName`それを修復している間に開きます。 場合`lpszName`が閉じられていないかが排他的に使用できる、エラーが発生します。  
  
 このメンバー関数が不完全な書き込み操作が不正であるとマークされたデータベースを修復しようとするとします。 これは、電源の停電やコンピューター ハードウェアの問題のため、Microsoft Jet データベース エンジンを使用するアプリケーションが予期せず終了した場合に発生します。 操作と呼び出しを完了する場合、[閉じる](../../mfc/reference/cdaodatabase-class.md#close)またはメンバー関数は、通常の方法でアプリケーションを終了、データベースはマークされません不正であるとします。  
  
> [!NOTE]
>  データベースを修復した後もを使用して圧縮することをお勧めします[CompactDatabase](#compactdatabase)メンバー関数のファイルを最適化して、ディスク領域を解放します。  
  
 データベースの修復の詳細については、DAO ヘルプの「RepairDatabase メソッド」を参照してください。  
  
##  <a name="a-namerollbacka--cdaoworkspacerollback"></a><a name="rollback"></a>CDaoWorkspace::Rollback  
 このメンバー関数を呼び出して、現在のトランザクションを終了し、トランザクションが開始する前の状態に、ワークスペース内のすべてのデータベースを復元します。  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  1 つのワークスペース オブジェクト内では、トランザクションは常に、ワークスペースにグローバルと、データベースまたはレコード セットの&1; つだけに限定されません。 1 つ以上のデータベースやワークスペースのトランザクション内でレコード セットに対する操作を実行する場合**ロールバック**すべてのデータベースとレコード セットのすべての操作を復元します。  
  
 保存または保留中のトランザクションをロールバックせず workspace オブジェクトを閉じると、トランザクションは自動的にロールバックします。 呼び出した場合[CommitTrans](#committrans)または**ロールバック**最初に呼び出さず[BeginTrans](#begintrans)エラーが発生します。  
  
> [!NOTE]
>  トランザクションを開始するときに、データベース エンジンは、ワークステーションで TEMP 環境変数で指定したディレクトリに置かれるファイルにその操作を記録します。 データベース エンジンがスローする MFC を発生する場合は、トランザクション ログ ファイルには、一時ドライブに空き容量が不足、 `CDaoException` (DAO エラー 2004)。 この時点で呼び出す場合**CommitTrans**、コミットされる操作の数が、残りの未完了の操作は失われ、操作を再起動する必要があります。 呼び出す**ロールバック**トランザクション ログを解放し、トランザクション内のすべての操作をロールバックします。  
  
##  <a name="a-namesetdefaultpassworda--cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a>CDaoWorkspace::SetDefaultPassword  
 パスワードを指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のパスワードを設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPassword`  
 既定のパスワード。 パスワードは、長さは最大 14 文字し、ASCII 0 (null) を除く任意の文字を含めることができます。 パスワードは、大文字小文字が区別されます。  
  
### <a name="remarks"></a>コメント  
 呼び出し後に作成した新しいワークスペースに設定する既定のパスワードが適用されます。 その後、ワークスペースを作成するときにパスワードを指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトは、呼び出す必要はありません**作成**します。  
  
2.  呼び出す`SetDefaultPassword`し、必要に応じて、 [SetDefaultUser](#setdefaultuser)します。  
  
3.  呼び出す**作成**この workspace オブジェクトまたはその後のパスワードを指定せずします。  
  
 既定では、デフォルト プロパティは"admin"に設定し、DefaultPassword プロパティが空の文字列 ("") です。  
  
 詳細については、セキュリティは、「DAO ヘルプの"アクセス許可のプロパティ"」を参照してください。 関連情報については、"DefaultPassword Property"DAO ヘルプの「デフォルト プロパティ」のトピックを参照してください。  
  
##  <a name="a-namesetdefaultusera--cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a>CDaoWorkspace::SetDefaultUser  
 特定のユーザー名を指定せずにワークスペースを作成するときに、データベース エンジンが使用する既定のユーザー名を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDefaultUser`  
 既定のユーザー名。 ユーザー名は 1 ~ 20 文字で指定し、アルファベット文字、アクセント記号付き文字、数字、スペース、および記号を含める:"(引用符)/(スラッシュ)、\\ (円記号) \[ \] (かっこ): (コロン) |(パイプ) \< (小さい-不等号)、> (大きい-不等号)、+ (正符号) = (等価な記号) です。(セミコロン) を (コンマ) (疑問符) * (アスタリスク)、先頭スペース、および制御文字 (ASCII 00 ASCII 31)。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
### <a name="remarks"></a>コメント  
 呼び出し後に作成した新しいワークスペースに設定する既定のユーザー名が適用されます。 その後、ワークスペースを作成するときに ユーザー名を指定する必要はありません、[作成](#create)呼び出します。  
  
 このメンバー関数を使用します。  
  
1.  構築、`CDaoWorkspace`オブジェクトは、呼び出す必要はありません**作成**します。  
  
2.  呼び出す`SetDefaultUser`し、必要に応じて、 [SetDefaultPassword](#setdefaultpassword)します。  
  
3.  呼び出す**作成**この workspace オブジェクトまたはその後のユーザー名を指定せずします。  
  
 既定では、デフォルト プロパティは"admin"に設定し、DefaultPassword プロパティが空の文字列 ("") です。  
  
 関連情報については、"デフォルト Property"DAO ヘルプの「DefaultPassword プロパティ」のトピックを参照してください。  
  
##  <a name="a-namesetinipatha--cdaoworkspacesetinipath"></a><a name="setinipath"></a>CDaoWorkspace::SetIniPath  
 Microsoft Jet データベース エンジンの Windows レジストリ設定の場所を指定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszRegistrySubkey*  
 Microsoft Jet データベース エンジンの設定やインストール可能な ISAM データベースに必要なパラメーターの位置を表す Windows レジストリのサブキーの名前を表す文字列。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetIniPath`特別な設定を指定する必要がある場合にのみです。 詳細については、DAO ヘルプの「IniPath プロパティ」を参照してください。  
  
> [!NOTE]
>  呼び出す`SetIniPath`アプリケーションのインストール中にないアプリケーションを実行します。 `SetIniPath`すべてのワークスペース、データベース、またはレコード セットを開く前に呼び出す必要があります。それ以外の場合、MFC は、例外をスローします。  
  
 このメカニズムを使用して、ユーザーが指定したレジストリ設定をデータベース エンジンを構成することができます。 この属性のスコープはアプリケーションに制限され、変更、アプリケーションを再起動する必要があります。  
  
##  <a name="a-namesetisolateodbctransa--cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a>CDaoWorkspace::SetIsolateODBCTrans  
 ワークスペースの DAO IsolateODBCTrans プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIsolateODBCTrans*  
 渡す**TRUE**特定 ODBC トランザクションを開始する場合。 渡す**FALSE** ODBC トランザクションの分離を停止する場合。  
  
### <a name="remarks"></a>コメント  
 いくつかの状況では、同じ ODBC データベース上に保留中の複数の同時トランザクションが必要があります。 これを行うには、トランザクションごとに独立したワークスペースを開く必要があります。 各ワークスペースには、データベースへの独自の ODBC 接続できますが、このシステムのパフォーマンスが低下します。 トランザクションの分離が必要ないため、同じユーザーによって開かれた複数のワークスペースのオブジェクトからの ODBC 接続は既定で共有されます。  
  
 Microsoft SQL Server などの一部の ODBC サーバーでは、単一の接続での同時トランザクションは許可されません。 保留中のようなデータベースで同時に複数のトランザクションがある場合に IsolateODBCTrans プロパティを設定**TRUE**を開くとすぐには、各ワークスペースにします。 これにより、各ワークスペースの別の ODBC 接続されます。  
  
##  <a name="a-namesetlogintimeouta--cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a>CDaoWorkspace::SetLoginTimeout  
 ワークスペースの DAO LoginTimeout プロパティの値を設定するには、このメンバー関数を呼び出します。  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `nSeconds`  
 ODBC データベースにログインしようとすると、エラーが発生するまでの秒数。  
  
### <a name="remarks"></a>コメント  
 この値は、ODBC データベースにログインしようとすると、エラーが発生するまでの秒数を表します。 既定の LoginTimeout 設定は、20 秒です。 LoginTimeout が 0 に設定されている場合は、タイムアウトが発生せず、データ ソースとの通信が応答を停止する可能性があります。  
  
 ネットワーク エラーの結果、接続が失敗するが、Microsoft SQL Server などの ODBC データベースにログインしようとするか、サーバーが実行されていないためです。 待機している既定の 20 秒間の接続のではなく、データベース エンジンがエラーを生成するまでに待機する時間を指定できます。 サーバーへのログオンは、外部サーバーのデータベースに対するクエリの実行など、さまざまなイベントの数値の一部として暗黙的に発生します。 タイムアウト値は LoginTimeout プロパティの現在の設定によって決まります。  
  
 関連情報については、DAO ヘルプの「LoginTimeout プロパティ」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)

