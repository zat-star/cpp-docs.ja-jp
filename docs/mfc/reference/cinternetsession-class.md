---
title: "CInternetSession クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetSession
dev_langs:
- C++
helpviewer_keywords:
- CInternetSession class
- Internet sessions
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
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
ms.openlocfilehash: caec3ae416dc82d49fc0051f0d9d1d2e021e0ba5
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetsession-class"></a>CInternetSession クラス
単一のインターネット セッションまたは複数の同時インターネット セッションを作成し、初期化します。必要な場合は、プロキシ サーバーへの接続も記述します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInternetSession : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetSession::CInternetSession](#cinternetsession)|`CInternetSession` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetSession::Close](#close)|インターネット セッションが終了した場合に、インターネット接続を閉じます。|  
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|ステータス コールバック ルーチンを確立します。|  
|[CInternetSession::GetContext](#getcontext)|インターネット セッションが終了した場合に、インターネット接続を閉じます。|  
|[CInternetSession::GetCookie](#getcookie)|指定した URL とその親のすべての Url の cookie を返します。|  
|[CInternetSession::GetCookieLength](#getcookielength)|バッファーに格納されているクッキーの長さを指定する値を取得します。|  
|[CInternetSession::GetFtpConnection](#getftpconnection)|サーバーと FTP セッションを開きます。 ユーザーをログオンします。|  
|[代わり](#getgopherconnection)|Gopher サーバーは接続を開こうとしているアプリケーションを開きます。|  
|[代わりに](#gethttpconnection)|接続を開こうとしているアプリケーションの HTTP サーバーを開きます。|  
|[:Onstatuscallback](#onstatuscallback)|ステータス コールバックが有効になっている場合は、操作のステータスを更新します。|  
|[できます](#openurl)|解析し、URL が開かれます。|  
|[CInternetSession::SetCookie](#setcookie)|指定された URL の cookie を設定します。|  
|[CInternetSession::SetOption](#setoption)|インターネット セッションのオプションを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](#operator_hinternet)|現在のインターネット セッションへのハンドル。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションの実行中には、インターネット接続を維持しなければならない場合、は、作成、`CInternetSession`クラスのメンバー [CWinApp](../../mfc/reference/cwinapp-class.md)します。  
  
 インターネット セッションが確立されると、呼び出す[OpenURL](#openurl)します。 `CInternetSession`グローバル関数を呼び出すことにより、URL を解析[AfxParseURL](http://msdn.microsoft.com/library/505c717e-aa52-4106-8522-eedff3d9bbae)します。 そのプロトコルの種類に関係なく`CInternetSession`URL を解釈し、管理、します。 URL リソース file:// で識別されるローカル ファイルに対する要求を処理できます。 `OpenURL`ポインターを返す、 [CStdioFile](../../mfc/reference/cstdiofile-class.md)オブジェクトの名前を渡す場合に、ローカル ファイルです。  
  
 使用してインターネット サーバーの URL を開くかどうか`OpenURL`、サイトから情報を読み取ることができます。 に対して、サーバー上にあるファイル (例、HTTP、FTP、または gopher) 用のサービスに固有のアクションを実行する場合は、そのサーバーに適切な接続を確立する必要があります。 特定の種類の特定のサービスに直接接続を開くには、次のメンバー関数を使用します。  
  
- [GetGopherConnection](#getgopherconnection) gopher サービスへの接続を開きます。  
  
- [GetHttpConnection](#gethttpconnection)を HTTP サービスへの接続を開きます。  
  
- [GetFtpConnection](#getftpconnection)を FTP サービスへの接続を開きます。  
  
 [SetOption](#setoption)タイムアウト値、再試行の回数など、セッションのクエリ オプションを設定したりすることができます。  
  
 `CInternetSession`メンバー関数[SetCookie](#setcookie)、 [GetCookie](#getcookie)、および[GetCookieLength](#getcookielength)サーバーとスクリプトの状態に関する情報を保持クライアント ワークステーション Win32 cookie データベースを管理する手段を提供します。  
  
 インターネットの基本的なプログラミング タスクの詳細については、記事を参照してください。[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)します。 MFC WinInet クラスの使用の詳細については、記事を参照してください。 [WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
> [!NOTE]
> `CInternetSession`スローされます、 [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)サポートされていないサービスの種類。 現在サポートされている次のサービスの種類のみ: FTP、HTTP、gopher、およびファイルです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="a-namecinternetsessiona--cinternetsessioncinternetsession"></a><a name="cinternetsession"></a>CInternetSession::CInternetSession  
 このメンバー関数が呼び出されます、`CInternetSession`オブジェクトを作成します。  
  
```  
CInternetSession(
    LPCTSTR pstrAgent = NULL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,  
    LPCTSTR pstrProxyName = NULL,  
    LPCTSTR pstrProxyBypass = NULL,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrAgent`  
 アプリケーションまたはインターネットの機能 (たとえば、「Microsoft インターネット ブラウザー」) を呼び出してエンティティ名前を識別する文字列へのポインター。 場合`pstrAgent`は**NULL** (既定)、フレームワークが、グローバル関数を呼び出す[AfxGetAppName](application-information-and-management.md#afxgetappname)アプリケーションの名前を表す null で終わる文字列を返します。 一部のプロトコルでは、この文字列を使用して、サーバーにアプリケーションを識別します。  
  
 `dwContext`  
 操作のコンテキストの識別子です。 `dwContext`によって返される操作のステータス情報を識別する[:onstatuscallback](#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はそのコンテキスト ID に関連付けられる  
  
 `dwAccessType`  
 必要なアクセスの種類。 以下は、有効な値を正確に&1; つを指定することがあります。  
  
- **INTERNET_OPEN_TYPE_PRECONFIG**レジストリ内の既存の設定を使用して接続します。 このアクセスの種類は、既定値として設定されます。 TIS プロキシ経由で接続、次のように設定します。 `dwAccessType` ; でこの値にする、レジストリを適切に設定します。  
  
- `INTERNET_OPEN_TYPE_DIRECT`インターネットに直接接続します。  
  
- `INTERNET_OPEN_TYPE_PROXY`CERN プロキシ経由で接続します。  
  
 プロキシのさまざまな種類と接続する方法については、次を参照してください。[典型的な FTP クライアント アプリケーションのステップ](../../mfc/steps-in-a-typical-ftp-client-application.md)します。  
  
 *pstrProxyName*  
 優先 CERN プロキシの名前場合`dwAccessType`として設定されている`INTERNET_OPEN_TYPE_PROXY`します。 既定値は**NULL**します。  
  
 *pstrProxyBypass*  
 サーバーのアドレスのオプションの一覧を含む文字列へのポインター。 プロキシへのアクセスを使用する場合は、これらのアドレスをバイパスすることがあります。 場合、 **NULL**値を指定して、バイパス リストは、レジストリから読み取られます。 このパラメーターは、意味のある場合にのみ、`dwAccessType`に設定されている`INTERNET_OPEN_TYPE_PROXY`します。  
  
 `dwFlags`  
 さまざまなキャッシュ オプションを示します。 既定値は 0 に設定されます。 使用可能な値は次のとおりです。  
  
- `INTERNET_FLAG_DONT_CACHE`ローカルまたはゲートウェイ サーバーのいずれかに、データをキャッシュしません。  
  
- `INTERNET_FLAG_OFFLINE`ダウンロード操作が終わったら、永続的なキャッシュのみを使用します。 項目がキャッシュに存在しない場合は、該当するエラー コードが返されます。 このフラグは、演算子と組み合わせることも`OR`( **|**) 演算子。  
  
### <a name="remarks"></a>コメント  
 **CInternetSession**はアプリケーションによって呼び出される最初のインターネット関数です。 内部データ構造体を初期化し、アプリケーションからの以降の呼び出しを準備します。  
  
 インターネット接続を開くことができる場合`CInternetSession`がスローされます、 [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb)します。  
  
### <a name="example"></a>例  
  例を参照してください[関数](../../mfc/reference/cftpfilefind-class.md)します。  
  
##  <a name="a-nameclosea--cinternetsessionclose"></a><a name="close"></a>CInternetSession::Close  
 使用して、アプリケーションが終了すると、このメンバー関数を呼び出して、`CInternetSession`オブジェクトです。  
  
```  
virtual void Close();
```  
  
### <a name="example"></a>例  
  例を参照してください[関数](../../mfc/reference/cftpfilefind-class.md)します。  
  
##  <a name="a-nameenablestatuscallbacka--cinternetsessionenablestatuscallback"></a><a name="enablestatuscallback"></a>CInternetSession::EnableStatusCallback  
 ステータス コールバックを有効にするには、このメンバー関数を呼び出します。  
  
```  
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 コールバックを有効または無効になっているかどうかを指定します。 既定値は**TRUE**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ステータス コールバックを処理する場合は、アプリケーションのステータス バーに (名前の解決、サーバーに接続する) などの操作の進行状況に関するステータスを指定できます。 操作の状態を表示するは、長期的な操作中に特に必要です。  
  
 コールバック生じないため、要求の処理中に、アプリケーションは、ネットワークへのデータのスループットの低下を防止するためのコールバックでできるだけ時間を節約する必要があります。 たとえば、コールバックではダイアログ ボックスを配置するには、時間のかかる操作、サーバーが要求を終了する可能性があります。  
  
 ステータス コールバックは、いずれかのコールバックが保留になっている限り削除できません。  
  
 すべての操作を非同期的に処理するためには、独自のスレッドを作成するか、MFC を使わない WinInet 関数を使用する必要があります。  
  
##  <a name="a-namegetcontexta--cinternetsessiongetcontext"></a><a name="getcontext"></a>CInternetSession::GetContext  
 このメンバー関数を呼び出して、特定のアプリケーション セッションのコンテキスト値を取得します。  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーション定義のコンテキストの識別子。  
  
### <a name="remarks"></a>コメント  
 [OnStatusCallback](#onstatuscallback)によって返されるコンテキスト ID を使用して**GetContext**特定のアプリケーションの状態を報告します。 たとえば、ユーザーには、ステータス情報を返すのでは、インターネット要求がアクティブ化、ステータス コールバックはその特定の要求のステータスをレポートするコンテキスト ID を使用します。 場合は、ユーザーが&2; つの異なるインターネット要求がステータス情報を返す処理を伴う`OnStatusCallback`コンテキスト id を使用して、対応する要求の状態を返します。 そのため、すべてのステータス コールバック操作のコンテキスト識別子を使用し、セッションが終了するまでのセッションに関連付けられています。  
  
 非同期操作の詳細については、記事を参照してください。[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)します。  
  
##  <a name="a-namegetcookiea--cinternetsessiongetcookie"></a><a name="getcookie"></a>CInternetSession::GetCookie  
 このメンバー関数は、Win32 関数の動作を実装して[InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPTSTR pstrCookieData,  
    DWORD dwBufLen);

 
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    CString& strCookieData);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrUrl`  
 URL を含む文字列へのポインター。  
  
 `pstrCookieName`  
 指定された URL を取得する cookie の名前を含む文字列へのポインター。  
  
 `pstrCookieData`  
 最初のオーバー ロードで cookie データを受信するバッファーのアドレスを含む文字列へのポインター。 この値は、 **NULL**します。 2 番目のオーバー ロードへの参照で、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) cookie データを格納するオブジェクト。  
  
 `dwBufLen`  
 サイズを指定する変数、`pstrCookieData`バッファー。 バッファーにコピーするデータの量を受け取る関数が成功した場合、`pstrCookieData`バッファー。 場合`pstrCookieData`は**NULL**、このパラメーターは、cookie のすべてのデータをコピーするために必要なバッファーのサイズを指定する値を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、または**FALSE**それ以外の場合。 呼び出しに失敗した場合は、Win32 関数を呼び出して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定します。 次のエラー値が適用されます。  
  
- **ERROR_NO_MORE_ITEMS**指定された URL の cookie とそのすべての親はありません。  
  
- **ERROR_INSUFFICIENT_BUFFER**に渡された値`dwBufLen`cookie のすべてのデータをコピーするには不十分です。 返された値`dwBufLen`バッファーのサイズはすべてのデータを取得するために必要なします。  
  
### <a name="remarks"></a>コメント  
 2 番目のオーバー ロードでは、MFC、cookie にデータを取得、指定された`CString`オブジェクトです。  
  
##  <a name="a-namegetcookielengtha--cinternetsessiongetcookielength"></a><a name="getcookielength"></a>CInternetSession::GetCookieLength  
 このメンバー関数を呼び出して、バッファーに格納されているクッキーの長さを取得します。  
  
```  
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrUrl`  
 URL を含む文字列へのポインター  
  
 `pstrCookieName`  
 クッキーの名前を含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`バッファーに格納されているクッキーの長さを示す値。 によって示される名前のない cookie の場合は&0; を`pstrCookieName`が存在します。  
  
### <a name="remarks"></a>コメント  
 この値を使用して[GetCookie](#getcookie)します。  
  
##  <a name="a-namegetftpconnectiona--cinternetsessiongetftpconnection"></a><a name="getftpconnection"></a>CInternetSession::GetFtpConnection  
 FTP 接続を確立しへのポインターを取得するには、このメンバー関数を呼び出して、`CFtpConnection`オブジェクトです。  
  
```  
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrServer`  
 FTP サーバーの名前を含む文字列へのポインター。  
  
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
  
 `bPassive`  
 この FTP セッションのパッシブまたはアクティブ モードを指定します。 場合に設定**TRUE**、Win32 API を設定して`dwFlag`に**INTERNET_FLAG_PASSIVE**します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、[詳細](../../mfc/reference/cftpconnection-class.md)オブジェクトです。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `GetFtpConnection`FTP サーバーに接続しを作成してへのポインターを返します、**詳細**オブジェクトです。 サーバー上の特定の操作は行われません。 ファイルに対する読み取りまたは書き込みする場合は、たとえば、別の手順としてこれらの操作を実行する必要があります。 クラスを参照してください[詳細](../../mfc/reference/cftpconnection-class.md)と[関数](../../mfc/reference/cftpfilefind-class.md)ファイルの検索について、ファイルを開くと読み取り/書き込みファイルにします。 記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)FTP 接続の一般的なタスクを実行する手順についてです。  
  
### <a name="example"></a>例  
  例を参照してください[関数](../../mfc/reference/cftpfilefind-class.md)します。  
  
##  <a name="a-namegetgopherconnectiona--cinternetsessiongetgopherconnection"></a><a name="getgopherconnection"></a>代わり  
 Gopher の新しい接続を確立しへのポインターを取得するには、このメンバー関数を呼び出して、`CGopherConnection`オブジェクトです。  
  
```  
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrServer`  
 Gopher サーバー名を含む文字列へのポインター。  
  
 `pstrUserName`  
 ユーザー名を含む文字列へのポインター。  
  
 `pstrPassword`  
 アクセスのパスワードを含む文字列へのポインター。  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
### <a name="return-value"></a>戻り値  
 ポインター、[関数](../../mfc/reference/cgopherconnection-class.md)オブジェクトです。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `GetGopherConnection`gopher サーバーに接続しを作成してへのポインターを返します、`CGopherConnection`オブジェクトです。 サーバー上の特定の操作は行われません。 データを読み取ったり書き込んだりする場合は、たとえば、別の手順としてこれらの操作を実行する必要があります。 クラスを参照してください[関数](../../mfc/reference/cgopherconnection-class.md)、 [CGopherFile](../../mfc/reference/cgopherfile-class.md)、および[関数](../../mfc/reference/cgopherfilefind-class.md)ファイルの検索について、ファイルを開くと読み取り/書き込みファイルにします。 FTP サイトを参照する方法については、メンバー関数を参照してください。 [OpenURL](#openurl)します。 記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)gopher 接続の一般的なタスクを実行する手順についてです。  
  
##  <a name="a-namegethttpconnectiona--cinternetsessiongethttpconnection"></a><a name="gethttpconnection"></a>代わりに  
 HTTP 接続を確立しへのポインターを取得するには、このメンバー関数を呼び出して、`CHttpConnection`オブジェクトです。  
  
```  
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);

 
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrServer`  
 HTTP サーバー名を含む文字列へのポインター。  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
 `pstrUserName`  
 ユーザー名を含む文字列へのポインター。  
  
 `pstrPassword`  
 アクセスのパスワードを含む文字列へのポインター。  
  
 *dwflags*  
 任意の組み合わせ、 **INTERNET_ _ flag _\* **フラグ。 表を参照して、**解説**の[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)の詳細については`dwFlags`値。  
  
### <a name="return-value"></a>戻り値  
 ポインター、[関数](../../mfc/reference/chttpconnection-class.md)オブジェクトです。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `GetHttpConnection`HTTP サーバーに接続しを作成してへのポインターを返します、`CHttpConnection`オブジェクトです。 サーバー上の特定の操作は行われません。 たとえば、HTTP ヘッダーを照会する場合は、個別の手順としては、この操作を実行する必要があります。 クラスを参照してください[関数](../../mfc/reference/chttpconnection-class.md)と[CHttpFile](../../mfc/reference/chttpfile-class.md)操作については、HTTP サーバーへの接続を使用して行うことができます。 HTTP サイトを参照する方法については、メンバー関数を参照してください。 [OpenURL](#openurl)します。 記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)一般的な HTTP 接続のタスクを実行する手順についてです。  
  
##  <a name="a-nameonstatuscallbacka--cinternetsessiononstatuscallback"></a><a name="onstatuscallback"></a>:Onstatuscallback  
 ステータス コールバックを有効にして、操作が保留中の状態を更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnStatusCallback(
    DWORD_PTR dwContext,  
    DWORD dwInternetStatus,  
    LPVOID lpvStatusInformation,  
    DWORD dwStatusInformationLength);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwContext`  
 アプリケーションによって提供されるコンテキストの値です。  
  
 `dwInternetStatus`  
 コールバックが行われる理由を示すステータス コード。 参照してください**解説**可能な値のテーブルにします。  
  
 `lpvStatusInformation`  
 このコールバックに関連する情報を格納するバッファーへのポインター。  
  
 `dwStatusInformationLength`  
 `lpvStatusInformation` のサイズ。  
  
### <a name="remarks"></a>コメント  
 最初に呼び出す必要があります[使用](#enablestatuscallback)ステータス コールバックを活用するためにします。  
  
 `dwInternetStatus`パラメーターは、実行中の操作を示すしの内容を決定`lpvStatusInformation`になります。 `dwStatusInformationLength`含まれるデータの長さを示す`lpvStatusInformation`します。 次の状態の値を`dwInternetStatus`次のように定義されています。  
  
|値|説明|  
|-----------|-------------|  
|`INTERNET_STATUS_RESOLVING_NAME`|含まれる名の IP アドレスを検索`lpvStatusInformation`します。|  
|`INTERNET_STATUS_NAME_RESOLVED`|含まれる名の IP アドレスを正常に見つかった`lpvStatusInformation`します。|  
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|ソケット アドレスへの接続 ( [SOCKADDR](../../mfc/reference/sockaddr-structure.md)) が指す`lpvStatusInformation`します。|  
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|ソケット アドレスに正常に接続されている ( `SOCKADDR`) が指す`lpvStatusInformation`します。|  
|`INTERNET_STATUS_SENDING_REQUEST`|サーバーに要求を送信します。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|**INTERNET_STATUS_ REQUEST_SENT**|サーバーに要求が正常に送信します。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|`INTERNET_STATUS_RECEIVING_RESPONSE`|サーバーの要求に応答を待機しています。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|`INTERNET_STATUS_RESPONSE_RECEIVED`|サーバーからの応答を受信しました。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|`INTERNET_STATUS_CLOSING_CONNECTION`|サーバーへの接続を閉じています。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|`INTERNET_STATUS_CONNECTION_CLOSED`|サーバーへの接続が正常に終了します。 `lpvStatusInformation`パラメーターは**NULL**します。|  
|`INTERNET_STATUS_HANDLE_CREATED`|Win32 API 関数で使用される[InternetConnect](http://msdn.microsoft.com/library/windows/desktop/aa384363)を新しいハンドルが作成されたことを示します。 これにより、アプリケーションの呼び出し、Win32 関数[InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350)接続時間がかかりすぎる場合、別のスレッドからです。 参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらの関数です。|  
|`INTERNET_STATUS_HANDLE_CLOSING`|このハンドルの値が正常に終了します。|  
  
 ステータス コールバック ルーチンが実行される前に、何らかのアクションを要求するには、この関数をオーバーライドします。  
  
> [!NOTE]
>  状態のコールバックには、スレッド状態の保護が必要があります。 MFC の共有ライブラリを使用している場合は、オーバーライドした関数の先頭に次の行を追加します。  
  
 [!code-cpp[NVC_MFCHtmlHttp&#8;](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]  
  
 非同期操作の詳細については、記事を参照してください。[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)します。  
  
##  <a name="a-nameopenurla--cinternetsessionopenurl"></a><a name="openurl"></a>できます  
 HTTP サーバーを指定された要求を送信し、MIME 追加 RFC822 を指定するクライアントを許可するには、関数、または、要求と共に送信する HTTP ヘッダーは、このメンバーを呼び出します。  
  
```  
CStdioFile* OpenURL(
    LPCTSTR pstrURL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,  
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLength = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrURL*  
 読み取りを開始する URL の名前へのポインター。 Url のみファイルで始まる: ftp: gopher: または http: はサポートされています。 **アサート**場合*pszURL*は**NULL**します。  
  
 `dwContext`  
 コールバックで返されたハンドルを使用して、アプリケーション定義の値が渡されます。  
  
 `dwFlags`  
 この接続を処理する方法を示すフラグ。 参照してください**解説**詳細については、有効なフラグです。 有効なフラグは次のとおりです。  
  
- **INTERNET_FLAG_TRANSFER_ASCII**既定値です。 ファイルを ASCII テキストとして転送されます。  
  
- **INTERNET_FLAG_TRANSFER_BINARY**バイナリ ファイルとしてファイルを転送します。  
  
- `INTERNET_FLAG_RELOAD`ローカルにキャッシュされている場合でも、通信回線からデータを取得します。  
  
- `INTERNET_FLAG_DONT_CACHE`ローカルまたはすべてのゲートウェイのいずれかに、データをキャッシュしません。  
  
- `INTERNET_FLAG_SECURE`このフラグは、HTTP の要求のみに適用されます。 Secure Sockets Layer または率とネットワーク上のセキュリティで保護されたトランザクションの要求  
  
- **INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT**によって生成された新しい要求をサーバーに既存の接続を再利用可能であれば、 **OpenUrl**接続要求ごとに新しいセッションを作成する代わりにします。  
  
- **INTERNET_FLAG_PASSIVE** FTP サイトのために使用します。 パッシブ FTP を使用します。 併用[関数](../../mfc/reference/cinternetconnection-class.md)の`OpenURL`です。  
  
 `pstrHeaders`  
 HTTP サーバーに送信されるヘッダーを含む文字列へのポインター。  
  
 *dwHeadersLength*  
 追加のヘッダーの文字数。 これが-1 L である場合、`pstrHeaders`以外は、 **NULL**、し`pstrHeaders`を&0; にするには、終了され、長さが計算されたと見なされます。  
  
### <a name="return-value"></a>戻り値  
 FTP、GOPHER、HTTP、およびファイルの種類のインターネット サービスのみのファイル ハンドルを返します。 返します。 **NULL**解析に失敗した場合。  
  
 マウス ポインターを`OpenURL`を返しますが異なります*pszURL*のサービスの種類。 次の表は、可能なポインターを示しています。`OpenURL`返すことができます。  
  
|URL の種類|戻り値|  
|--------------|-------------|  
|file://|**CStdioFile\***|  
|http://|**CHttpFile\***|  
|gopher://|**CGopherFile\***|  
|ftp://|**CInternetFile\***|  
  
### <a name="remarks"></a>コメント  
 パラメーター`dwFlags`いずれかを含める必要があります**INTERNET_FLAG_TRANSFER_ASCII**または**INTERNET_FLAG_TRANSFER_BINARY**、両方ではないです。 その他のフラグは、演算子と組み合わせることができます`OR`演算子 ( **|**)。  
  
 `OpenURL`、Win32 関数をラップする**InternetOpenURL**、唯一のダウンロード、取得、およびインターネット サーバーからデータを読み取りを許可します。 `OpenURL`その必要のないように、リモートの場所にファイル操作許可されません[関数](../../mfc/reference/cinternetconnection-class.md)オブジェクトです。  
  
 特定の接続を使用する (つまり、プロトコル固有) 関数、ファイルへの書き込みなどする必要がありますセッションを開始し、特定の種類の接続を開くその接続を使用して、目的のモードでファイルを開きます。 参照してください`CInternetConnection`の接続に固有の関数に関する詳細情報。  
  
##  <a name="a-nameoperatorhinterneta--cinternetsessionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetSession::operator HINTERNET  
 この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="a-namesetcookiea--cinternetsessionsetcookie"></a><a name="setcookie"></a>CInternetSession::SetCookie  
 指定された URL の cookie を設定します。  
  
```  
static BOOL SetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPCTSTR pstrCookieData);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrUrl`  
 Cookie を設定する URL を指定する null で終わる文字列へのポインター。  
  
 `pstrCookieName`  
 クッキーの名前を含む文字列へのポインター。  
  
 `pstrCookieData`  
 URL に関連付ける実際の文字列データを含む文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、または**FALSE**それ以外の場合。 特定のエラー コードを取得する**GetLastError します。**  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetoptiona--cinternetsessionsetoption"></a><a name="setoption"></a>CInternetSession::SetOption  
 インターネット セッションのオプションを設定するには、このメンバー関数を呼び出します。  
  
```  
BOOL SetOption(
    DWORD dwOption,  
    LPVOID lpBuffer,  
    DWORD dwBufferLength,  
    DWORD dwFlags = 0);

 
BOOL SetOption(
    DWORD dwOption,  
    DWORD dwValue,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwOption`  
 インターネット オプションを設定します。 参照してください[オプション フラグ](http://msdn.microsoft.com/library/windows/desktop/aa385328)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]使用可能なオプションの一覧についてです。  
  
 `lpBuffer`  
 オプションの設定を格納するバッファー。  
  
 *dwBufferLength*  
 長さ`lpBuffer`のサイズまたは`dwValue`です。  
  
 `dwValue`  
 A`DWORD`オプション設定が含まれています。  
  
 `dwFlags`  
 さまざまなキャッシュ オプションを示します。 既定値は 0 に設定されます。 使用可能な値は次のとおりです。  
  
- `INTERNET_FLAG_DONT_CACHE`ローカルまたはゲートウェイ サーバーのいずれかに、データをキャッシュしません。  
  
- `INTERNET_FLAG_OFFLINE`ダウンロード操作が終わったら、永続的なキャッシュのみを使用します。 項目がキャッシュに存在しない場合は、該当するエラー コードが返されます。 このフラグは、演算子と組み合わせることも`OR`( **|**) 演算子。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合、値は**TRUE**が返されます。 エラーが発生しました、値の場合**FALSE**が返されます。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cinternetconnection-class.md)   
 [関数のクラス](../../mfc/reference/chttpconnection-class.md)   
 [クラスの詳細](../../mfc/reference/cftpconnection-class.md)   
 [関数のクラス](../../mfc/reference/cgopherconnection-class.md)

