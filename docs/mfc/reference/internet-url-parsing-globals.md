---
title: "インターネット URL 解析用グローバル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 3aec259acae2f5e9c9b65ac4e5c898ca57ff3d52
ms.lasthandoff: 02/24/2017

---
# <a name="internet-url-parsing-globals"></a>インターネット URL 解析用グローバル関数
クライアントはインターネット サーバーにクエリを送信するときは、クライアントに関する情報を抽出するのに URL 解析用グローバルのいずれかを使用できます。  
  
### <a name="internet-url-parsing-globals"></a>インターネット URL 解析用グローバル関数  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|URL 文字列を解析し、サービスとそのコンポーネントの型を返します。|  
|[AfxParseURLEx](#afxparseurlex)|URL 文字列を解析し、サービスとそのコンポーネントだけでなく、ユーザー名とパスワードの種類を取得します。|  
  
##  <a name="a-nameafxparseurla--afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL  
 このグローバルで使用される[できます](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
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
 サービスの種類を次の URL の最初のセグメント。  
  
 `strObject`  
 URL を表すオブジェクト (空でもかまいません)。  
  
 `nPort`  
 いずれかが存在する場合に、URL のサーバーまたはオブジェクトのいずれかの部分から決定されます。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、URL は正常に解析されました。これが空か、既知のインターネット サービスの種類が含まれていない場合、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 URL 文字列を解析し、サービスとそのコンポーネントの型を返します。  
  
 たとえば、 `AfxParseURL` 、形式の Url を解析して**service://server/dir/dir/object.ext:port**し、次のように格納されているそのコンポーネントを返します。  
  
 `strServer`"server"= =  
  
 `strObject`= ="/dir/dir/object/object.ext"  
  
 `nPort`#port = =  
  
 `dwServiceType`#service = =  
  
> [!NOTE]
>  この関数を呼び出すには、プロジェクトは AFXINET を含める必要があります。H.  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxinet.h  
  
##  <a name="a-nameafxparseurlexa--afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx  
 このグローバル関数は、拡張のバージョン[AfxParseURL](#afxparseurl)で使用されると[できます](../../mfc/reference/cinternetsession-class.md#openurl)します。  
  
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
 サービスの種類を次の URL の最初のセグメント。  
  
 `strObject`  
 URL を表すオブジェクト (空でもかまいません)。  
  
 `nPort`  
 いずれかが存在する場合に、URL のサーバーまたはオブジェクトのいずれかの部分から決定されます。  
  
 *strUsername*  
 参照、`CString`ユーザーの名前を表すオブジェクト。  
  
 `strPassword`  
 参照、`CString`ユーザーのパスワードを表すオブジェクト。  
  
 `dwFlags`  
 URL を解析する方法を制御するフラグ。 次の値の組み合わせにすることができます。  
  
|値|説明|  
|-----------|-------------|  
|**ICU_DECODE**|%XX エスケープ シーケンスを文字に変換します。|  
|**ICU_NO_ENCODE**|安全でない文字をエスケープ シーケンスに変換されません。|  
|**ICU_NO_META**|(「\」などのメタ シーケンスを削除しないでください。 および「\..」)URL です。|  
|**ICU_ENCODE_SPACES_ONLY**|スペースだけをエンコードします。|  
|**ICU_BROWSER_MODE**|エンコードまたは '#' の後に文字をデコードまたは '後の末尾の空白文字を削除しないでくださいと' です。 この値が指定されていない場合は、URL 全体がエンコードされ、後続の空白が削除されます。|  
  
 変換が安全でない文字とメタ シーケンスのすべてのフラグがなければ、MFC の既定を使用する場合 (など\\.、\..、および\\...) をエスケープ シーケンスです。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、URL は正常に解析されました。これが空か、既知のインターネット サービスの種類が含まれていない場合、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 URL 文字列を解析し、サービスとそのコンポーネントだけでなく、ユーザーの名前とパスワードを入力の型を返します。 フラグがどのように安全でない文字を指定の処理です。  
  
> [!NOTE]
>  この関数を呼び出すには、プロジェクトは AFXINET を含める必要があります。H.  

### <a name="requirements"></a>要件  
  **ヘッダー** afxinet.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

