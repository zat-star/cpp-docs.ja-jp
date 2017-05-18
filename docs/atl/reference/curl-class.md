---
title: "クラスの cUrl |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
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
ms.openlocfilehash: eda63a8dc704dd471d8078b848d95fc9fb44f58f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="curl-class"></a>CUrl クラス
このクラスは、URL を表します。 既存の URL を解析するかどうか、他のユーザーとは無関係に URL の各要素を操作できる文字列または最初から文字列を作成します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CUrl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CUrl::CUrl](#curl)|コンストラクターです。|  
|[CUrl:: ~ CUrl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|URL 文字列を正規の形式に変換するためには、このメソッドを呼び出します。|  
|[CUrl::Clear](#clear)|すべての URL フィールドをクリアするには、このメソッドを呼び出します。|  
|[CUrl::CrackUrl](#crackurl)|デコードし、URL を解析するには、このメソッドを呼び出します。|  
|[CUrl::CreateUrl](#createurl)|このメソッドでは、URL を作成します。|  
|[CUrl::GetExtraInfo](#getextrainfo)|余分な情報を取得するには、このメソッドを呼び出す (よう*テキスト*または #*テキスト*) の URL からです。|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|追加の情報の長さを取得するには、このメソッドを呼び出す (など*テキスト*または #*テキスト*) を URL から取得します。|  
|[CUrl::GetHostName](#gethostname)|URL からホスト名を取得するには、このメソッドを呼び出します。|  
|[CUrl::GetHostNameLength](#gethostnamelength)|ホスト名の長さを取得するのには、このメソッドを呼び出します。|  
|[CUrl::GetPassword](#getpassword)|URL からパスワードを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetPasswordLength](#getpasswordlength)|パスワードの長さを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetPortNumber](#getportnumber)|ATL_URL_PORT の観点からポート番号を取得するには、このメソッドを呼び出します。|  
|[CUrl::GetScheme](#getscheme)|URL スキームを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetSchemeName](#getschemename)|URL スキーム名を取得するには、このメソッドを呼び出します。|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|URL スキーム名の長さを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetUrlLength](#geturllength)|URL の長さを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetUrlPath](#geturlpath)|URL パスを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|URL パスの長さを取得するには、このメソッドを呼び出します。|  
|[CUrl::GetUserName](#getusername)|URL からユーザー名を取得するには、このメソッドを呼び出します。|  
|[CUrl::GetUserNameLength](#getusernamelength)|ユーザー名の長さを取得するには、このメソッドを呼び出します。|  
|[CUrl::SetExtraInfo](#setextrainfo)|余分な情報を設定するには、このメソッドを呼び出す (など*テキスト*または #*テキスト*) の URL。|  
|[CUrl::SetHostName](#sethostname)|ホスト名を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetPassword](#setpassword)|パスワードを設定するには、このメソッドを呼び出します。|  
|[CUrl::SetPortNumber](#setportnumber)|ATL_URL_PORT の観点からポート番号を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetScheme](#setscheme)|URL スキームを設定するには、このメソッドを呼び出します。|  
|[スキーム](#setschemename)|URL スキーム名を設定するには、このメソッドを呼び出します。|  
|[CUrl::SetUrlPath](#seturlpath)|URL パスを設定するには、このメソッドを呼び出します。|  
|[CUrl::SetUserName](#setusername)|ユーザー名を設定するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|指定された割り当て`CUrl`現在オブジェクト`CUrl`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CUrl`パスやポート番号などの URL のフィールドを操作できます。 `CUrl`次の形式の Url を認識します。  
  
 \<スキーム >://\<UserName >:\<パスワード > @\<HostName >:\<PortNumber >/\<UrlPath >\<ExtraInfo >  
  
 (一部のフィールドは、省略可能)。たとえば、この URL があるとします。  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl)次のように解析します。  
  
-   スキーム:"http"または[ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   ユーザー名:"someone"  
  
-   パスワード:「シークレット」  
  
-   ホスト名:"www.microsoft.com"  
  
-   ポート番号: 80  
  
-   UrlPath:"visualc/stuff.htm"  
  
-   ExtraInfo:"#contents"  
  
 UrlPath フィールドを (たとえば) を操作するには、使用[GetUrlPath](#geturlpath)、 [GetUrlPathLength](#geturlpathlength)、および[SetUrlPath](#seturlpath)します。 使用する[CreateUrl](#createurl)を完全な URL 文字列を作成します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="canonicalize"></a>CUrl::Canonicalize  
 URL 文字列を正規の形式に変換するためには、このメソッドを呼び出します。  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 正規化を制御するフラグ。 フラグが指定されていない場合 ( `dwFlags` = 0)、メソッドは、すべての安全でない文字とメタ シーケンスに変換します。 (など\\。、\..、および\\...) をエスケープ シーケンスです。 `dwFlags`次の値のいずれかを指定できます。  
  
-   ATL_URL_BROWSER_MODE: はエンコードまたは「#」の後に文字をデコードまたは""、末尾の空白文字の後に削除されません""です。 この値が指定されていない場合は、URL 全体がエンコードされ、後続の空白が削除されます。  
  
-   ATL_URL _DECODE: 文字のエスケープ シーケンスを含む URL が解析される前にすべての %XX シーケンスに変換します。  
  
-   ATL_URL _ENCODE_PERCENT: 見つかったパーセント記号を任意にエンコードします。 既定では、パーセント記号はエンコードされていません。  
  
-   ATL_URL _ENCODE_SPACES_ONLY: 空白文字だけをエンコードします。  
  
-   ATL_URL _NO_ENCODE: 安全でない文字をエスケープ シーケンスでは変換されません。  
  
-   ATL_URL _NO_META: メタ シーケンスは削除されません (など"です。"と"..") の URL からです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 正規の形式に変換するには、安全でない文字とスペースをエスケープ シーケンスを変換します。  
  
##  <a name="clear"></a>CUrl::Clear  
 すべての URL フィールドをクリアするには、このメソッドを呼び出します。  
  
```
inline void Clear() throw();
```  
  
##  <a name="crackurl"></a>CUrl::CrackUrl  
 デコードし、URL を解析するには、このメソッドを呼び出します。  
  
```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszUrl`  
 URL です。  
  
 `dwFlags`  
 指定のすべてのエスケープ文字を変換するには、ATL_URL_DECODE または ATL_URL_ESCAPE`lpszUrl`に解析後に実際の値。 (Visual C 2005 以前 ATL_URL_DECODE 変換すべてのエスケープ文字を解析する前にします。)  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="createurl"></a>CUrl::CreateUrl  
 このメソッドは、CUrl オブジェクトのコンポーネントのフィールドから文字列を URL を構築します。  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszUrl*  
 完全な URL 文字列を保持する文字列バッファー。  
  
 `pdwMaxLength`  
 最大長、 *lpszUrl*文字列バッファー。  
  
 `dwFlags`  
 内のすべてのエスケープ文字に変換する ATL_URL_ESCAPE 指定*lpszUrl*に実際の値。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、次の形式を使用して完全な URL 文字列を作成するために個別のフィールドを追加します。  
  
 **\<スキーム >://\<ユーザー >:\<渡す > @\<ドメイン >:\<ポート >\<パス >\<余分な >**  
  
 このメソッドを呼び出すときに、`pdwMaxLength`パラメーターにによって参照される文字列バッファーの最大長は最初に、 *lpszUrl*パラメーター。 値、`pdwMaxLength`パラメーターを URL 文字列の実際の長さで更新されます。  
  
### <a name="example"></a>例  
 このサンプルでは、CUrl オブジェクトとその URL 文字列を取得するの作成  
  
 [!code-cpp[NVC_ATL_Utilities #&133;](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="curl"></a>CUrl::CUrl  
 コンストラクターです。  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `urlThat`  
 `CUrl` URL の作成にコピーするオブジェクト。  
  
##  <a name="dtor"></a>CUrl:: ~ CUrl  
 デストラクターです。  
  
```
~CUrl() throw();
```  
  
##  <a name="getextrainfo"></a>CUrl::GetExtraInfo  
 余分な情報を取得するには、このメソッドを呼び出す (よう*テキスト*または #*テキスト*) の URL からです。  
  
```
inline LPCTSTR GetExtraInfo() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 追加情報を含む文字列を返します。  
  
##  <a name="getextrainfolength"></a>CUrl::GetExtraInfoLength  
 追加の情報の長さを取得するには、このメソッドを呼び出す (など*テキスト*または #*テキスト*) を URL から取得します。  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 追加情報を含む文字列の長さを返します。  
  
##  <a name="gethostname"></a>CUrl::GetHostName  
 URL からホスト名を取得するには、このメソッドを呼び出します。  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ホスト名を返します。  
  
##  <a name="gethostnamelength"></a>CUrl::GetHostNameLength  
 ホスト名の長さを取得するのには、このメソッドを呼び出します。  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ホスト名の長さを返します。  
  
##  <a name="getpassword"></a>CUrl::GetPassword  
 URL からパスワードを取得するには、このメソッドを呼び出します。  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 パスワードを返します。  
  
##  <a name="getpasswordlength"></a>CUrl::GetPasswordLength  
 パスワードの長さを取得するには、このメソッドを呼び出します。  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 パスワードの長さを返します。  
  
##  <a name="getportnumber"></a>CUrl::GetPortNumber  
 ポート番号を取得するには、このメソッドを呼び出します。  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポート番号を返します。  
  
##  <a name="getscheme"></a>CUrl::GetScheme  
 URL スキームを取得するには、このメソッドを呼び出します。  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。、 [ATL_URL_SCHEME](atl-url-scheme-enum.md) URL のスキームを記述する値。  
  
##  <a name="getschemename"></a>CUrl::GetSchemeName  
 URL スキーム名を取得するには、このメソッドを呼び出します。  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 URL のスキーム名 ("http"、"ftp"など) を返します。  
  
##  <a name="getschemenamelength"></a>CUrl::GetSchemeNameLength  
 URL スキーム名の長さを取得するには、このメソッドを呼び出します。  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 URL のスキーム名の長さを返します。  
  
##  <a name="geturllength"></a>CUrl::GetUrlLength  
 URL の長さを取得するには、このメソッドを呼び出します。  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 URL の長さを返します。  
  
##  <a name="geturlpath"></a>CUrl::GetUrlPath  
 URL パスを取得するには、このメソッドを呼び出します。  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 URL パスを返します。  
  
##  <a name="geturlpathlength"></a>CUrl::GetUrlPathLength  
 URL パスの長さを取得するには、このメソッドを呼び出します。  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 URL パスの長さを返します。  
  
##  <a name="getusername"></a>CUrl::GetUserName  
 URL からユーザー名を取得するには、このメソッドを呼び出します。  
  
```
inline LPCTSTR GetUserName() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザー名を返します。  
  
##  <a name="getusernamelength"></a>CUrl::GetUserNameLength  
 ユーザー名の長さを取得するには、このメソッドを呼び出します。  
  
```
inline DWORD GetUserNameLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザー名の長さを返します。  
  
##  <a name="operator_eq"></a>CUrl::operator =  
 指定された割り当て`CUrl`現在オブジェクト`CUrl`オブジェクトです。  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `urlThat`  
 `CUrl`現在のオブジェクトにコピーするオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトへの参照を返します。  
  
##  <a name="setextrainfo"></a>CUrl::SetExtraInfo  
 余分な情報を設定するには、このメソッドを呼び出す (など*テキスト*または #*テキスト*) の URL。  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszInfo*  
 URL に含める追加情報を含む文字列。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="sethostname"></a>CUrl::SetHostName  
 ホスト名を設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHost`  
 ホスト名です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="setpassword"></a>CUrl::SetPassword  
 パスワードを設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszPass*  
 パスワード。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="setportnumber"></a>CUrl::SetPortNumber  
 ポート番号を設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nPrt*  
 ポート番号。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="setscheme"></a>CUrl::SetScheme  
 URL スキームを設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nScheme`  
 いずれか、 [ATL_URL_SCHEME](atl-url-scheme-enum.md)スキームの値。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 名前、スキームを設定することもできます (を参照してください[スキーム](#setschemename))。  
  
##  <a name="setschemename"></a>スキーム  
 URL スキーム名を設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSchm*  
 URL のスキーム名。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 使用して、スキームを設定することも、 [ATL_URL_SCHEME](atl-url-scheme-enum.md)定数 (を参照してください[CUrl::SetScheme](#setscheme))。  
  
##  <a name="seturlpath"></a>CUrl::SetUrlPath  
 URL パスを設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPath`  
 URL パス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="setusername"></a>CUrl::SetUserName  
 ユーザー名を設定するには、このメソッドを呼び出します。  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszUser*  
 ユーザー名。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)

