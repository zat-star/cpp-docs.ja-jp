---
title: "CTokenPrivileges クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
dev_langs:
- C++
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
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
ms.openlocfilehash: 4d732dbf27c2155ffb98ca59b140d01ea92458e0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges クラス
このクラスは、用のラッパー、 **TOKEN_PRIVILEGES**構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|コンストラクターです。|  
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenPrivileges::Add](#add)|1 つ以上の特権が追加、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::Delete](#delete)|特権を削除、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::DeleteAll](#deleteall)|すべての特権を削除、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetCount](#getcount)|特権のエントリの数を返します、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|取得の表示名に含まれている特権、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetLength](#getlength)|バッファー サイズを保持するために必要なバイト数で返します、 **TOKEN_PRIVILEGES**構造によって表されます、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|ローカル一意識 (別子 Luid) とから属性のフラグを取得、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|権限の名前と属性のフラグから取得、`CTokenPrivileges`オブジェクトです。|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|ポインターを返す、 **TOKEN_PRIVILEGES**構造体。|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|指定した特権名に関連付けられている属性を取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|値へのポインターをキャスト、 **TOKEN_PRIVILEGES**構造体。|  
|[CTokenPrivileges::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストについて説明し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。  
  
 アクセス トークンを使用して、各ユーザーに与えられているさまざまなセキュリティ特権を記述します。 特権は、ローカルに一意の識別子と呼ばれる 64 ビットの数値で構成されています ( [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)) と記述子の文字列です。  
  
 `CTokenPrivileges`クラスのラッパーである、 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)構造体し、0 または多くの権限が含まれています。 削除、または指定されたクラスのメソッドを使用して照会された特権を追加することができます。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="add"></a>CTokenPrivileges::Add  
 1 つ以上の特権が追加、`CTokenPrivileges`アクセス トークンのオブジェクト。  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。  
  
 `bEnable`  
 True の場合、特権が有効にします。 False の場合、この特権は無効です。  
  
 `rPrivileges`  
 参照、 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)構造体。 特権と属性がこの構造体からコピーされに追加された、`CTokenPrivileges`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの最初の形式は、特権が正常に追加された場合、false それ以外の場合は true を返します。  
  
##  <a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges  
 コンストラクターです。  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CTokenPrivileges`新しいオブジェクトに割り当てるオブジェクト。  
  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)に割り当てる新しい構造`CTokenPrivileges`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `CTokenPrivileges`を使用してオブジェクトを作成することができます必要に応じて、 **TOKEN_PRIVILEGES**構造体または以前に定義された`CTokenPrivileges`オブジェクトです。  
  
##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges  
 デストラクターです。  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、割り当てられているすべてのリソースを解放します。  
  
##  <a name="delete"></a>CTokenPrivileges::Delete  
 特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。 たとえば、このパラメーター指定定数 SE_SECURITY_NAME、またはそれに対応する文字列を"SeSecurityPrivilege"  
  
### <a name="return-value"></a>戻り値  
 特権があった場合、false を正常に削除されたそれ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows 2000 上で制限付きトークンを作成するためのツールとして役立ちます。  
  
##  <a name="deleteall"></a>CTokenPrivileges::DeleteAll  
 すべての特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 含まれているすべての特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。  
  
##  <a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames  
 取得の表示名に含まれている特権、`CTokenPrivileges`アクセス トークンのオブジェクト。  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisplayNames`  
 `CString` オブジェクトの配列へのポインター。 **CNames** typedef と定義: **CTokenPrivileges::CAtlArray\<CString >**します。  
  
### <a name="remarks"></a>コメント  
 パラメーター`pDisplayNames`の配列へのポインターは、`CString`オブジェクトに格納されている権限に対応する表示名が表示される`CTokenPrivileges`オブジェクトです。 このメソッドは、WINNT の権限の定義のセクションで指定された権限のみの表示名を取得します。H.  
  
 このメソッドは、表示可能な名前を取得しますたとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合は、表示可能な名前は、"強制シャット ダウン、リモート システムからです。"。 システム名を取得するには使用[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)します。  
  
##  <a name="getcount"></a>CTokenPrivileges::GetCount  
 特権のエントリの数を返します、`CTokenPrivileges`オブジェクトです。  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 含まれる権限の数を返します、`CTokenPrivileges`オブジェクトです。  
  
##  <a name="getlength"></a>CTokenPrivileges::GetLength  
 長さを返す、`CTokenPrivileges`オブジェクトです。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 保持するために必要なバイト数を返す、 **TOKEN_PRIVILEGES**構造によって表されます、`CTokenPrivileges`などが含まれている特権エントリをすべてのオブジェクト。  
  
##  <a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes  
 ローカル一意識 (別子 Luid) とから属性のフラグを取得、`CTokenPrivileges`オブジェクトです。  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPrivileges`  
 配列を指すポインター [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)オブジェクトです。 **CLUIDArray** typedef 定義として**CAtlArray\<LUID > CLUIDArray**します。  
  
 `pAttributes`  
 DWORD オブジェクトの配列へのポインター。 このパラメーターが省略されるか NULL の場合は、属性は取得されません。 **CAttributes** typedef 定義として**CAtlArray \<DWORD > CAttributes**します。  
  
### <a name="remarks"></a>コメント  
 このメソッドはすべてに含まれる権限の列挙は、`CTokenPrivileges`トークンのオブジェクトにアクセスし、それぞれの Luid および (必要に応じて) 属性のフラグの配列オブジェクトに移動します。  
  
##  <a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes  
 名前と属性のフラグを取得、`CTokenPrivileges`オブジェクトです。  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNames*  
 配列を指すポインター`CString`オブジェクトです。 **CNames** typedef 定義として**CAtlArray \<CString > Cname**します。  
  
 `pAttributes`  
 DWORD オブジェクトの配列へのポインター。 このパラメーターが省略されるか NULL の場合は、属性は取得されません。 **CAttributes** typedef 定義として**CAtlArray \<DWORD > CAttributes**します。  
  
### <a name="remarks"></a>コメント  
 このメソッドはすべてに含まれる権限の列挙は、`CTokenPrivileges`オブジェクト、配列オブジェクトに、名前と、(必要に応じて) 属性のフラグを配置することです。  
  
 このメソッドは、表示可能な名前ではなく、属性名を取得しますたとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合は、システム名"を返します。"。 表示可能な名前を取得するメソッドを使用して[CTokenPrivileges::GetDisplayNames](#getdisplaynames)します。  
  
##  <a name="getptoken_privileges"></a>CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 ポインターを返す、 **TOKEN_PRIVILEGES**構造体。  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)構造体。  
  
##  <a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege  
 指定した特権名に関連付けられている属性を取得します。  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。 たとえば、このパラメーター指定定数 SE_SECURITY_NAME、またはそれに対応する文字列を"SeSecurityPrivilege"  
  
 `pdwAttributes`  
 属性が格納される変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 属性は正常に取得された、false をそれ以外の場合がある場合に true を返します。  
  
##  <a name="operator_eq"></a>CTokenPrivileges::operator =  
 代入演算子。  
  
```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)に割り当てる構造、`CTokenPrivileges`オブジェクトです。  
  
 `rhs`  
 `CTokenPrivileges`オブジェクトに割り当てるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CTokenPrivileges`オブジェクトです。  
  
##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges::operator const TOKEN_PRIVILEGES *  
 値へのポインターをキャスト、 **TOKEN_PRIVILEGES**構造体。  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 値へのポインターをキャスト、 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)構造体。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID_AND_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

