---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- protocols, HTTP
- connecting to servers, HTTP servers
- Internet protocols, HTTP
- HTTP connections
- Internet protocols
- CHttpConnection class
- HTTP servers, connecting to
- connecting to servers
- Internet connections, HTTP
- connections [C++], HTTP
- Internet server, HTTP
ms.assetid: a402b662-c445-4988-800d-c8278551babe
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1b02a79cebbd73a05478887115646f0544f0a92d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="chttpconnection-class"></a>関数のクラス
HTTP サーバーへの接続を管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|
          `CHttpConnection` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[しないで](#openrequest)|HTTP 要求を開きます。|  
  
## <a name="remarks"></a>コメント  
 HTTP は、MFC WinInet クラスによって実装される&3; つのインターネット サーバー プロトコルのいずれかです。  
  
 クラス`CHttpConnection`コンス トラクターと&1; つのメンバー関数を含む[OpenRequest](#openrequest)、HTTP プロトコルを使ってサーバーへの接続を管理します。  
  
 HTTP サーバーと通信するためのインスタンスを最初に作成する必要があります[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、作成、[関数](#_mfc_chttpconnection)オブジェクトです。 作成しないで、`CHttpConnection`オブジェクトに直接を呼び出す[代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)、作成、`CHttpConnection`オブジェクトし、ポインターを返します。  
  
 方法について説明する`CHttpConnection`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。 詳細については、他の&2; つを使用してサーバーに接続するには、インターネット プロトコル、gopher、FTP がサポートされる、クラスを参照してください。[関数](../../mfc/reference/cgopherconnection-class.md)と[詳細](../../mfc/reference/cftpconnection-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 このメンバー関数が作成すると呼ばれる、`CHttpConnection`オブジェクトです。  
  
```  
CHttpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 ポインター、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。  
  
 `hConnected`  
 インターネット接続へのハンドル。  
  
 `pstrServer`  
 サーバー名を含む文字列へのポインター。  
  
 `dwContext`  
 コンテキスト識別子、`CInternetConnection`オブジェクトです。 参照してください**解説**の詳細については`dwContext`です。  
  
 `nPort`  
 この接続のインターネットのポートを識別する番号。  
  
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
  
 `dwFlags`  
 任意の組み合わせ、 **INTERNET_ _ flag _\* **フラグ。 表を参照して、**解説**の[しないで](#openrequest)の詳細については`dwFlags`値。  
  
### <a name="remarks"></a>コメント  
 作成しないで、`CHttpConnection`直接します。 呼び出してオブジェクトを作成する代わりに、[代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)します。  
  
##  <a name="openrequest"></a>しないで  
 このメンバー関数を呼び出して HTTP 接続を開きます。  
  
```  
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

 
CHttpFile* OpenRequest(
    int nVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrVerb`  
 要求で使用する動詞を含む文字列へのポインター。 `NULL` の場合、"GET" が使用されます。  
  
 `pstrObjectName`  
 指定した動詞のターゲット オブジェクトを含む文字列へのポインター。 これは一般的に、ファイル名、実行可能モジュール、または検索指定子です。  
  
 `pstrReferer`  
 元のドキュメントのアドレス (URL) を指定する文字列へのポインター、要求内の URL ( `pstrObjectName`) を取得しました。 `NULL` の場合、HTTP ヘッダーは指定されません。  
  
 `dwContext`  
 `OpenRequest` 操作のコンテキスト識別子。 `dwContext` の詳細については、「解説」を参照してください。  
  
 `ppstrAcceptTypes`  
 クライアントが受け入れるコンテンツ タイプを示す文字列への `LPCTSTR` ポインターの配列 (終端は null) へのポインター。 `ppstrAcceptTypes` が `NULL` の場合、クライアントが "text/*" 形式のドキュメントのみ (つまり画像やその他のバイナリ ファイルではなくテキスト ドキュメントのみ) を受け入れると、サーバーは解釈します。 コンテンツ タイプは CGI 変数 CONTENT_TYPE と同等です。HTTP POST や PUT など情報が添付されるクエリのデータの形式を識別します。  
  
 `pstrVersion`  
 HTTP バージョンを定義する文字列へのポインター。 `NULL` の場合、"HTTP/1.0" が使用されます。  
  
 `dwFlags`  
 INTERNET_ FLAG_* フラグの任意の組み合わせ。 使用できる `dwFlags` 値の説明については、「解説」を参照してください。  
  
 `nVerb`  
 HTTP 要求の種類に関連付けられた番号。 次のいずれかの値を指定します。  
  
|HTTP 要求の種類|`nVerb` の値|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CHttpFile](../../mfc/reference/chttpfile-class.md)要求のあったオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `dwFlags` は次のいずれかになります。  
  
|インターネット フラグ|説明|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|要求されたファイル、オブジェクト、またはディレクトリ リストをキャッシュからではなく元のサーバーからダウンロードします。|  
|`INTERNET_FLAG_DONT_CACHE`|返されたエンティティをキャッシュに追加しません。|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|返されたエンティティを永続エンティティとしてキャッシュに追加します。 つまり、標準的なキャッシュのクリーンアップ、整合性チェック、またはガベージ コレクションでは、キャッシュからこの項目を削除することはできません。|  
|`INTERNET_FLAG_SECURE`|安全なトランザクション セマンティクスを使用します。 これは、SSL/PCT を使用するように変換され、HTTP 要求でのみ意味があります。|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|HTTP でのみ使用をリダイレクトする必要がある自動で処理されないことを指定[chttpfile::sendrequest](../../mfc/reference/chttpfile-class.md#sendrequest)します。|  
  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子がこの特定の操作に関連付けられている、`CHttpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトです。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)識別は操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
 この関数では例外がスローされる場合があります。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile クラス](../../mfc/reference/chttpfile-class.md)

