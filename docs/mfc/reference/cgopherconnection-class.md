---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherConnection
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- Internet server, gopher
- connecting to servers, gopher servers
- protocols, gopher
- services, gopher
- CGopherConnection class
- gopher protocol
- gopher server
- connecting to servers
- Internet connections, gopher
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
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
ms.openlocfilehash: 6267dd226e87e5bf64faa7225e49d9a99af93e3e
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherconnection-class"></a>関数のクラス
gopher インターネット サーバーへの接続を管理します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームで機能しませんが、以前のプラットフォームで動作し続けますので、そのメンバーは廃止されました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|`CGopherConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|作成、[関数](../../mfc/reference/cgopherlocator-class.md)gopher サーバー上のファイルを検索するオブジェクト。|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher オブジェクトの属性情報を取得します。|  
|[CGopherConnection::OpenFile](#openfile)|Gopher ファイルを開きます。|  
  
## <a name="remarks"></a>コメント  
 Gopher サービスでは、MFC WinInet クラスによって認識される&3; つのインターネット サービスの&1; つです。  
  
 クラス`CGopherConnection`コンス トラクターと gopher サービスを管理する&3; つの追加のメンバー関数が含まれています: [OpenFile](#openfile)、 [CreateLocator](#createlocator)、および[GetAttribute](#getattribute)します。  
  
 Gopher インターネット サーバーと通信するためのインスタンスを最初に作成する必要があります[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、呼び出す[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)、作成、`CGopherConnection`オブジェクトし、ポインターを返します。 作成しないで、`CGopherConnection`オブジェクトに直接します。  
  
 方法について説明する`CGopherConnection`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。 FTP および HTTP クラスを参照してください、その他の&2; つの使用に関する詳細については、インターネット サービスをサポートされる、[関数](../../mfc/reference/chttpconnection-class.md)と[詳細](../../mfc/reference/cftpconnection-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="a-namecgopherconnectiona--cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopherConnection::CGopherConnection  
 このメンバー関数が作成すると呼ばれる、`CGopherConnection`オブジェクトです。  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。  
  
 `hConnected`  
 現在のインターネット セッションの Windows ハンドル。  
  
 `pstrServer`  
 FTP サーバーの名前を含む文字列へのポインター。  
  
 `dwContext`  
 操作のコンテキストの識別子です。 `dwContext`によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はそのコンテキスト ID に関連付けられる  
  
 `pstrUserName`  
 ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 場合**NULL**、既定値は匿名です。  
  
 `pstrPassword`  
 ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方`pstrPassword`と`pstrUserName`は**NULL**、匿名の既定のパスワードは、ユーザーの電子メール名。 場合`pstrPassword`は**NULL** (または空の文字列) が、`pstrUserName`は**NULL**、空白のパスワードを使用します。 次の表の&4; 種類の設定では、動作`pstrUserName`と`pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されるパスワード|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL**または""|**NULL**または""|「匿名」|ユーザーの電子メール名|  
|非- **NULL**文字列|**NULL**または""|`pstrUserName`|" "|  
|**NULL**以外**NULL**文字列|**エラー**|**エラー**||  
|非- **NULL**文字列|非- **NULL**文字列|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CGopherConnection`直接します。 代わりに、呼び出す[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)を作成する、`CGopherConnection`オブジェクトし、ポインターを返します。  
  
##  <a name="a-namecreatelocatora--cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopherConnection::CreateLocator  
 検索または gopher サーバー上のファイルを識別する gopher ロケーターを作成するには、このメンバー関数を呼び出します。  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDisplayString`  
 Gopher ドキュメントまたは取得するディレクトリの名前を含む文字列へのポインター。 場合、`pstrDisplayString`パラメーターは**NULL**、gopher サーバーの既定のディレクトリが返されます。  
  
 `pstrSelectorString`  
 項目を取得するために、gopher サーバーに送信されるセレクター文字列へのポインター。 `pstrSelectorString`できる**NULL**します。  
  
 *dwGopherType*  
 これを指定するかどうか`pstrSelectorString`ディレクトリや、ドキュメントを参照および要求が gopher か gopher + です。 構造体の属性を参照してください[GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pstrLocator`  
 開くファイルを識別する文字列へのポインター。 この文字列がへの呼び出しから返された一般的に、[なった](../../mfc/reference/cgopherfilefind-class.md#getlocator)します。  
  
 *pstrServerName*  
 Gopher サーバー名を含む文字列へのポインター。  
  
 `nPort`  
 この接続のインターネットのポートを識別する番号。  
  
### <a name="return-value"></a>戻り値  
 A[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 静的メンバー関数のバージョンでは、静的でないバージョンが、接続オブジェクトからサーバー名を使用して、サーバーを指定する必要があります。  
  
 Gopher サーバーから情報を取得するために、アプリケーションはまず gopher ロケーターを取得する必要があります。 アプリケーションはロケーターを不透明なトークンとして扱う必要がありますし、(は、アプリケーションことができます、ロケーターを使ってが直接ではなく操作または比較)。 アプリケーションは、ロケーターを使用して、呼び出しのために通常は、 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)特定の情報を取得します。  
  
##  <a name="a-namegetattributea--cgopherconnectiongetattribute"></a><a name="getattribute"></a>CGopherConnection::GetAttribute  
 Gopher サーバーから、その項目に関する情報を特定の属性を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトです。  
  
 *strRequestedAttributes*  
 要求された属性の名前を指定する、スペースで区切られた文字列。  
  
 `strResult`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)ロケーターの種類を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
##  <a name="a-nameopenfilea--cgopherconnectionopenfile"></a><a name="openfile"></a>CGopherConnection::OpenFile  
 Gopher サーバー上のファイルを開くには、このメンバー関数を呼び出します。  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクトです。  
  
 `dwFlags`  
 INTERNET_FLAG_ * フラグの組み合わせ。 参照してください[できます](../../mfc/reference/cinternetsession-class.md#openurl)INTERNET_FLAG_ の詳細については\*フラグ。  
  
 `pstrView`  
 ファイル ビューの文字列へのポインター。 ファイルのいくつかのビューは、サーバーに存在する場合は、ファイルを開くにはビューを指定します。 場合`pstrView`は**NULL**既定のファイルのビューを使用します。  
  
 `dwContext`  
 開いているファイルのコンテキスト ID。 参照してください**解説**の詳細については`dwContext`です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CGopherFile](../../mfc/reference/cgopherfile-class.md)開かれているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子がこの特定の操作に関連付けられている、`CGopherConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)識別は操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラスの詳細](../../mfc/reference/cftpconnection-class.md)   
 [関数のクラス](../../mfc/reference/chttpconnection-class.md)   
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [関数のクラス](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)

