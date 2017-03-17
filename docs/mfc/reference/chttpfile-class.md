---
title: "CHttpFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
dev_langs:
- C++
helpviewer_keywords:
- HTTP files
- HTTP requests, requesting and reading files
- CHttpFile class
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0077c04f53514901dccaa3d162cd132578270225
ms.lasthandoff: 02/24/2017

---
# <a name="chttpfile-class"></a>CHttpFile クラス
HTTP サーバー上のファイルを要求し、読み込む機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|
          `CHttpFile` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|HTTP サーバーに送信された要求にヘッダーを追加します。|  
|[CHttpFile::EndRequest](#endrequest)|HTTP サーバーに送信された要求を終了、 [SendRequestEx](#sendrequestex)メンバー関数。|  
|[CHttpFile::GetFileURL](#getfileurl)|指定したファイルの URL を取得します。|  
|[CHttpFile::GetObject](#getobject)|HTTP サーバーへの要求で、動詞のターゲット オブジェクトを取得します。|  
|[CHttpFile::GetVerb](#getverb)|HTTP サーバーへの要求で使用されている動詞を取得します。|  
|[CHttpFile::QueryInfo](#queryinfo)|HTTP サーバーから、応答または要求ヘッダーを返します。|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|HTTP 要求に関連付けられている状態コードを取得し、提供された配置`dwStatusCode`パラメーター。|  
|[Chttpfile::sendrequest](#sendrequest)|HTTP サーバーに要求を送信します。|  
|[CHttpFile::SendRequestEx](#sendrequestex)|使用して HTTP サーバーに要求を送信、[書き込み](../../mfc/reference/cinternetfile-class.md#write)または[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)方法`CInternetFile`します。|  
  
## <a name="remarks"></a>コメント  
 インスタンスを作成する必要がある場合は、インターネット セッションでは、HTTP サーバーからデータを読み取り、`CHttpFile`です。  
  
 方法について説明する`CHttpFile`他のインターネットの MFC クラスと動作は、記事を参照して[WinInet を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders  
 1 つを追加するには、このメンバー関数を呼び出すか、HTTP 要求に複数の HTTP 要求ヘッダーを処理します。  
  
```  
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,  
    int dwHeadersLen = -1);

 
BOOL AddRequestHeaders(
    CString& str,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrHeaders`  
 ヘッダーまたは要求に追加するヘッダーを含む文字列へのポインター。 各ヘッダーは、CR/LF の組み合わせで終わる必要があります。  
  
 `dwFlags`  
 新しいヘッダーのセマンティクスを変更します。 次のいずれかの値を指定します。  
  
- `HTTP_ADDREQ_FLAG_COALESCE`最初の後続のヘッダーにヘッダーを追加するフラグを使用して、同じ名前のヘッダーをマージします。 たとえば、"Accept: テキスト/*"続く"Accept: オーディオ/\*"1 つのヘッダーの形成に"Accept: テキスト/\*、オーディオ/\*"です。 まとめられた、または別のヘッダーで送信された要求が受信したデータに関する結合方式のように、呼び出し元のアプリケーションの責任です。  
  
- `HTTP_ADDREQ_FLAG_REPLACE`削除を実行し、現在のヘッダーを置き換えるに追加します。 ヘッダー名は、現在のヘッダーを削除するために使用され、新しいヘッダーを追加するすべての値が使用されます。 ヘッダー値が空のヘッダーが見つかった場合は削除されます。 指定しない場合、空で、ヘッダー値が置き換えられます。  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`既に存在しない場合、ヘッダーを追加します。 1 つが存在する場合、エラーが返されます。  
  
- `HTTP_ADDREQ_FLAG_ADD`置換に使用されます。 存在しない場合は、ヘッダーを追加します。  
  
 `dwHeadersLen`  
 長さを文字数の`pstrHeaders`です。 場合は-1 L をし、これは`pstrHeaders`0 で終了すると想定し、長さが計算されます。  
  
 `str`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)要求ヘッダーまたは追加するヘッダーを格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 `AddRequestHeaders`HTTP 要求ハンドルを追加の自由な形式のヘッダーを追加します。 使用するため、HTTP サーバーに送信された正確な要求の詳細に制御を必要とするクライアントによってです。  
  
> [!NOTE]
>  アプリケーションで複数のヘッダーを渡すことができます`pstrHeaders`または`str`の`AddRequestHeaders`を使用して呼び出す`HTTP_ADDREQ_FLAG_ADD`または`HTTP_ADDREQ_FLAG_ADD_IF_NEW`です。 アプリケーションが削除または置換を使用してヘッダーを試むかどうか**HTTP_ADDREQ_FLAG_REMOVE**または`HTTP_ADDREQ_FLAG_REPLACE`、1 つだけのヘッダーを指定する`lpszHeaders`です。  
  
##  <a name="chttpfile"></a>CHttpFile::CHttpFile  
 このメンバー関数が作成すると呼ばれる、`CHttpFile`オブジェクトです。  
  
```  
CHttpFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrObject,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrVerb,  
    DWORD_PTR dwContext);

 
CHttpFile(
    HINTERNET hFile,  
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObject,  
    CHttpConnection* pConnection);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 インターネット ファイルへのハンドル。  
  
 `hSession`  
 インターネット セッションへのハンドル。  
  
 *pstrObject*  
 含む文字列へのポインター、`CHttpFile`オブジェクトです。  
  
 `pstrServer`  
 サーバーの名前を含む文字列へのポインター。  
  
 `pstrVerb`  
 要求を送信するときに使用されるメソッドを含む文字列へのポインター。 Can be **POST**, **HEAD**, or `GET`.  
  
 独自  
 コンテキスト識別子、`CHttpFile`オブジェクトです。 参照してください**解説**の詳細については、このパラメーターにします。  
  
 `pConnection`  
 ポインター、[関数](../../mfc/reference/chttpconnection-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 構築することはありません、`CHttpFile`オブジェクトに直接; 呼び出しではなく[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)代わりにします。  
  
 既定値`dwContext`MFC から送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクトです。 呼び出すと`CInternetSession::OpenURL`または`CHttpConnection`を構築する、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="endrequest"></a>CHttpFile::EndRequest  
 HTTP サーバーに送信された要求を終了するには、このメンバー関数を呼び出す、 [SendRequestEx](#sendrequestex)メンバー関数。  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 操作を記述するフラグ。 適切なフラグの一覧は、次を参照してください。 [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpBuffIn`  
 初期化されたへのポインター[記述](http://msdn.microsoft.com/library/windows/desktop/aa385132)操作に使用される入力バッファーを記述します。  
  
 `dwContext`  
 `CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 既定値`dwContext`MFC から送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクトです。 呼び出すと[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[関数](../../mfc/reference/chttpconnection-class.md)を構築する、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="getfileurl"></a>CHttpFile::GetFileURL  
 URL として HTTP ファイルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)このファイルに関連付けられているリソースを参照する URL を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、呼び出しは成功した後でのみ[SendRequest](#sendrequest)または、`CHttpFile`によって正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
##  <a name="getobject"></a>CHttpFile::GetObject  
 これに関連付けられているオブジェクトの名前を取得するには、このメンバー関数を呼び出す`CHttpFile`します。  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトの名前を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、呼び出しは成功した後でのみ[SendRequest](#sendrequest)または、`CHttpFile`によって正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
##  <a name="getverb"></a>CHttpFile::GetVerb  
 これに関連付けられている HTTP 動詞 (またはメソッド) を取得するには、このメンバー関数を呼び出す`CHttpFile`します。  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) HTTP 動詞 (またはメソッド) の名前を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、呼び出しは成功した後でのみ[SendRequest](#sendrequest)または、`CHttpFile`によって正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
##  <a name="queryinfo"></a>CHttpFile::QueryInfo  
 このメンバー関数を呼び出して応答を返すか、HTTP 要求からヘッダーを要求します。  
  
```  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    LPVOID lpvBuffer,  
    LPDWORD lpdwBufferLength,  
    LPDWORD lpdwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    CString& str,  
    LPDWORD dwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    SYSTEMTIME* pSysTime,  
    LPDWORD dwIndex = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwInfoLevel`  
 属性をクエリし、必要な情報の種類を指定する次のフラグの組み合わせです。  
  
- **ヘッダーが**、ヘッダー名を検索し、この値を返します`lpvBuffer`出力します。 **ヘッダーが**ヘッダーが見つからない場合にアサーションをスローします。  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS**通常応答ヘッダーに対してクエリを実行しますが、アプリケーションは、このフラグを使用して要求ヘッダーをクエリもできます。  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME**は「最終更新時刻、」などの日付/時刻型のヘッダーの場合は、このフラグは標準の Win32 とヘッダーの値を返します。 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)データを解析するアプリケーションを必要としない構造体。 このフラグを使用する場合は、使用することがある場合、`SYSTEMTIME`関数をオーバーライドします。  
  
- **HTTP_QUERY_FLAG_NUMBER**ヘッダーの値は、ステータス コードなどの数値の場合は、このフラグは 32 ビットの数値としてデータを返します。  
  
 参照してください、**解説**有効な値の一覧については、セクションです。  
  
 `lpvBuffer`  
 情報を受け取るバッファーへのポインター。  
  
 `lpdwBufferLength`  
 項目で、これは文字またはバイト数でのデータ バッファーの長さを示す値を指します。 参照してください、**解説**このパラメーターの詳細情報 セクションです。  
  
 `lpdwIndex`  
 ヘッダーの&0; から始まるインデックスへのポインター。 できる**NULL**します。 同じ名前の複数のヘッダーを列挙するのにには、このフラグを使用します。 入力に`lpdwIndex`返される指定したヘッダーのインデックスを示します。 出力では、`lpdwIndex`次のヘッダーのインデックスを示します。 次のインデックスが見つからない場合**見つからない**が返されます。  
  
 `str`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)返される情報を受け取るオブジェクト。  
  
 `dwIndex`  
 インデックス値。 「`lpdwIndex`」を参照してください。  
  
 *pSysTime*  
 Win32 へのポインター [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、呼び出しは成功した後でのみ[SendRequest](#sendrequest)または、`CHttpFile`によって正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
 データの次の種類を取得する`QueryInfo`:  
  
-   文字列 (既定)  
  
- `SYSTEMTIME`(の"データ:""有効期限:"など、ヘッダー)  
  
- `DWORD`(の**STATUS_CODE**、 **CONTENT_LENGTH**などです)。  
  
 文字列は、バッファーに書き込まれ、メンバー関数が成功すると、`lpdwBufferLength`文字列の終端の 1 を引いた数値文字の長さを含む**NULL**文字です。  
  
 可能性のある`dwInfoLevel`値が含まれます。  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>CHttpFile::QueryInfoStatusCode  
 HTTP 要求に関連付けられている状態コードを取得するには、このメンバー関数を呼び出すし、指定されたに配置`dwStatusCode`パラメーター。  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStatusCode`  
 状態コードへの参照。 状態コードは、要求されたイベントの成否を示します。 参照してください**解説**のステータス コードの説明を選択するためです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのには呼び出すことができます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、呼び出しは成功した後でのみ[SendRequest](#sendrequest)または、`CHttpFile`によって正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
 HTTP 状態コードは、成功または要求の失敗を示すグループに分類されます。 次の表は、ステータス コード グループと最も一般的な HTTP ステータス コードを示しています。  
  
|グループ化|説明|  
|-----------|-------------|  
|200-299|成功|  
|300-399|情報|  
|400-499|要求エラー|  
|500-599|サーバー エラー|  
  
 一般的な HTTP 状態コード:  
  
|状態コード|説明|  
|-----------------|-------------|  
|200|URL にある、伝送次のとおりです。|  
|400|解釈できない要求|  
|404|要求 URL が見つかりません。|  
|405|サーバーが要求されたメソッドをサポートしていません|  
|500|不明なサーバー エラー|  
|503|サーバーの容量に達しました|  
  
##  <a name="sendrequest"></a>Chttpfile::sendrequest  
 HTTP サーバーに要求を送信するには、このメンバー関数を呼び出します。  
  
```  
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLen = 0,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);

 
BOOL SendRequest(
    CString& strHeaders,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrHeaders`  
 送信するヘッダーの名前を含む文字列へのポインター。  
  
 `dwHeadersLen`  
 識別されるヘッダーの長さ`pstrHeaders`です。  
  
 `lpOptional`  
 任意の省略可能な要求ヘッダーの直後に送信するデータ。 これは通常、使用**POST**と**配置**操作します。 これは、 **NULL**を送信するオプションのデータがない場合。  
  
 *dwOptionalLen*  
 `lpOptional` の長さ。  
  
 `strHeaders`  
 送信される要求のヘッダーの名前を表す文字列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
##  <a name="sendrequestex"></a>CHttpFile::SendRequestEx  
 HTTP サーバーに要求を送信するには、このメンバー関数を呼び出します。  
  
```  
BOOL SendRequestEx(
    DWORD dwTotalLen,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);

 
BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,  
    LPINTERNET_BUFFERS lpBuffOut,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTotalLen*  
 要求で送信されるバイト数。  
  
 `dwFlags`  
 操作を記述するフラグ。 適切なフラグの一覧は、次を参照してください。 [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 `dwContext`  
 `CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。  
  
 `lpBuffIn`  
 初期化されたへのポインター[記述](http://msdn.microsoft.com/library/windows/desktop/aa385132)操作に使用される入力バッファーを記述します。  
  
 *lpBuffOut*  
 初期化されたへのポインター**記述**操作に使用される出力バッファーを記述します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合&0; 以外の値。 呼び出しに失敗した場合は、スローされたエラーの原因を判断する[表す](../../mfc/reference/cinternetexception-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この機能により、アプリケーションを使用してデータを送信する、[書き込み](../../mfc/reference/cinternetfile-class.md#write)と[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)方法`CInternetFile`します。 この関数の両方のオーバーライドを呼び出す前に送信するデータの長さを知る必要があります。 最初のオーバーライドでは、送信するデータの長さを指定することができます。 2 番目のオーバーライド**記述**構造体は、きわめて詳細な情報のバッファーの記述に使用できます。  
  
 コンテンツがファイルに書き込まれると、呼び出す[EndRequest](#endrequest)操作を終了します。  
  
 既定値`dwContext`MFC から送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクトです。 呼び出すと[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[関数](../../mfc/reference/chttpconnection-class.md)を構築する、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用するオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="example"></a>例  
 次のコード片は、文字列の内容を MFCISAPI という名前の DLL に送信します。ローカル ホスト サーバー上の DLL です。 この例は、1 つだけの呼び出しを使用して、 `WriteString`、複数の呼び出しを使用するブロックでデータを送信可能です。  
  
 [!code-cpp[NVC_MFCWinInet&#9;](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [関数のクラス](../../mfc/reference/chttpconnection-class.md)

