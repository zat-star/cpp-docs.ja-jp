---
title: "インターネット URL 解析用グローバル関数とヘルパー |Microsoft Docs"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 947ef992d58895e4638d9ffe77fca973cea8eada
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="internet-url-parsing-globals-and-helpers"></a>インターネット URL 解析用グローバル関数とヘルパー
クライアントはインターネット サーバーにクエリを送信するときは、クライアントに関する情報を抽出するのに URL 解析用グローバルのいずれかを使用できます。 ヘルパー関数では、その他のインターネット機能を提供します。
  
## <a name="internet-url-parsing-globals"></a>インターネット URL 解析用グローバル関数  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|URL 文字列を解析し、サービスとそのコンポーネントの型を返します。|  
|[AfxParseURLEx](#afxparseurlex)|URL 文字列を解析し、サービスとそのコンポーネントをできるだけでなく、ユーザー名とパスワードの種類を取得します。|  

## <a name="other-internet-helpers"></a>その他のインターネット ヘルパー
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|インターネット接続に関連する例外をスローします。|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|インターネット ハンドルの種類を決定します。|
  
##  <a name="afxparseurl"></a>AfxParseURL  
 このグローバル[できます](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrURL*  
 解析する URL を含む文字列へのポインター。  
  
 `dwServiceType`  
 インターネット サービスの種類を示します。 次の値を指定できます。  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 次のサービスの種類 URL の最初のセグメント。  
  
 `strObject`  
 URL を表すオブジェクト (空でもかまいません)。  
  
 `nPort`  
 いずれかが存在する場合に、URL のサーバーまたはオブジェクトのいずれかの部分から決定されます。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、URL は正常に解析されました。これが空か、既知のインターネット サービスの種類が含まれていない場合それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 URL 文字列を解析し、サービスとそのコンポーネントの型を返します。  
  
 たとえば、`AfxParseURL`フォームの Url を解析して**service://server/dir/dir/object.ext:port**し、次のように格納されているそのコンポーネントを返します。  
  
 `strServer`"server"= =  
  
 `strObject`= ="/dir/dir/object/object.ext"  
  
 `nPort`#port を = =  
  
 `dwServiceType`#service を = =  
  
> [!NOTE]
>  この関数を呼び出すには、プロジェクトは AFXINET を含める必要があります。H.  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxinet.h  
  
##  <a name="afxparseurlex"></a>AfxParseURLEx  
 このグローバル関数は、拡張のバージョン[AfxParseURL](#afxparseurl)で使用されると[できます](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrURL*  
 解析する URL を含む文字列へのポインター。  
  
 `dwServiceType`  
 インターネット サービスの種類を示します。 次の値を指定できます。  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 次のサービスの種類 URL の最初のセグメント。  
  
 `strObject`  
 URL を表すオブジェクト (空でもかまいません)。  
  
 `nPort`  
 いずれかが存在する場合に、URL のサーバーまたはオブジェクトのいずれかの部分から決定されます。  
  
 *strUsername*  
 参照、`CString`ユーザーの名前を表すオブジェクト。  
  
 `strPassword`  
 参照、`CString`ユーザーのパスワードを表すオブジェクト。  
  
 `dwFlags`  
 URL を解析する方法を制御するフラグ。 次の値の組み合わせが可能です。  
  
|値|説明|  
|-----------|-------------|  
|**ICU_DECODE**|%XX エスケープ シーケンスを文字に変換します。|  
|**ICU_NO_ENCODE**|安全でない文字をエスケープ シーケンスに変換されません。|  
|**ICU_NO_META**|(「\」などのメタ シーケンスを削除しないでください。 および「\..」)URL です。|  
|**ICU_ENCODE_SPACES_ONLY**|スペースだけをエンコードします。|  
|**ICU_BROWSER_MODE**|エンコードまたは '#' の後に文字をデコードまたは '後の末尾の空白文字を削除しない' です。 この値が指定されていない場合は、URL 全体をエンコードされ、後続の空白が削除されます。|  
  
 関数には、すべての認識できない文字とメタ シーケンスに変換しますフラグがない、MFC の既定を使用する場合 (など\\.、\..、および\\...) をエスケープ シーケンスです。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、URL は正常に解析されました。これが空か、既知のインターネット サービスの種類が含まれていない場合それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 URL 文字列を解析し、サービスとそのコンポーネントだけでなく、ユーザーの名前とパスワードを入力の型を返します。 フラグがどのように安全でない文字を指定処理されます。  
  
> [!NOTE]
>  この関数を呼び出すには、プロジェクトは AFXINET を含める必要があります。H.  

### <a name="requirements"></a>要件  
  **ヘッダー** afxinet.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>AfxGetInternetHandleType
インターネット ハンドルの種類を確認するのにには、この関数を使用します。  
   
### <a name="syntax"></a>構文  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>パラメーター  
 `hQuery`  
 インターネット クエリへのハンドル。  
   
### <a name="return-value"></a>戻り値  
 WININET で定義されているインターネット サービスの種類のいずれか。H. これらのインターネット サービスの一覧については、「解説」セクションを参照してください。 ハンドルは、null または認識されない、AFX_INET_SERVICE_UNK を返します。  
   
### <a name="remarks"></a>コメント  
 次の一覧には、によって返される使用可能なインターネット型が含まれています。`AfxGetInternetHandleType`です。  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  この関数を呼び出すために、プロジェクトは AFXINET を含める必要があります。H.  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>AfxThrowInternetException
インターネットの例外をスローします。  
   
### <a name="syntax"></a>構文    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>パラメーター  
 `dwContext`  
 エラーの原因となった操作のコンテキストの識別子です。 既定値の`dwContext`で最初に指定された[CInternetSession](cinternetsession-class.md)に渡されると[関数](cinternetconnection-class.md)- と[CInternetFile](cinternetfile-class.md)-派生クラス。 既定のオーバーライド通常の接続またはファイルで実行される特定の操作に対して、`dwContext`独自のです。 この値に返されます、 [:onstatuscallback](cinternetsession-class.md#onstatuscallback)を特定の操作の状態を識別します。 
  
 `dwError`  
 例外の原因となったエラー。  
   
### <a name="remarks"></a>コメント  
 オペレーティング システム エラー コードに基づく原因を特定するを担当しています。  
  
> [!NOTE]
>  この関数を呼び出すには、プロジェクトは AFXINET を含める必要があります。H.  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [CInternetException クラス](cinternetexception-class.md)   
 [スローします。](#throw)
 


