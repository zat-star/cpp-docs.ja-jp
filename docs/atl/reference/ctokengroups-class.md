---
title: "CTokenGroups クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
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
ms.openlocfilehash: 41b93e1c0a2e55013e280023a7f47610d38ddc10
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ctokengroups-class"></a>CTokenGroups クラス
このクラスは、用のラッパー、 **TOKEN_GROUPS**構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|コンストラクターです。|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|追加、`CSid`既存または**TOKEN_GROUPS**構造の`CTokenGroups`オブジェクトです。|  
|[CTokenGroups::Delete](#delete)|削除、`CSid`とその関連付けられた属性から、`CTokenGroups`オブジェクトです。|  
|[CTokenGroups::DeleteAll](#deleteall)|すべて削除`CSid`オブジェクトと、関連付けられた属性から、`CTokenGroups`オブジェクトです。|  
|[CTokenGroups::GetCount](#getcount)|数を返す`CSid`オブジェクトと関連付けられた属性に含まれている、 **CTokenGroups**オブジェクトです。|  
|[CTokenGroups::GetLength](#getlength)|サイズを返す、`CTokenGroups`オブジェクトです。|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|ポインターを取得、 **TOKEN_GROUPS**構造体。|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|取得、`CSid`オブジェクトと属性に属している、`CTokenGroups`オブジェクトです。|  
|[CTokenGroups::LookupSid](#lookupsid)|関連付けられている属性を取得、`CSid`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|キャスト、`CTokenGroups`オブジェクトへのポインターを**TOKEN_GROUPS**構造体。|  
|[CTokenGroups::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストについて説明し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。  
  
 **CTokenGroups**クラスのラッパーである、 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)構造、アクセス トークン内のグループ セキュリティ識別子 (Sid) に関する情報を格納します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="add"></a>CTokenGroups::Add  
 追加、`CSid`既存または**TOKEN_GROUPS**構造の`CTokenGroups`オブジェクトです。  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `dwAttributes`  
 属性に関連付ける、`CSid`オブジェクトです。  
  
 *rTokenGroups*  
 A [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)構造体。  
  
### <a name="remarks"></a>コメント  
 これらのメソッドが&1; つ以上追加`CSid`オブジェクトと、関連付けられた属性に、`CTokenGroups`オブジェクトです。  
  
##  <a name="ctokengroups"></a>CTokenGroups::CTokenGroups  
 コンストラクターです。  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CTokenGroups`オブジェクトまたは[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)構造が構築されると、`CTokenGroups`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `CTokenGroups`を使用してオブジェクトを作成することができます必要に応じて、 **TOKEN_GROUPS**構造体または以前に定義された`CTokenGroups`オブジェクトです。  
  
##  <a name="dtor"></a>CTokenGroups:: ~ CTokenGroups  
 デストラクターです。  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、割り当てられているすべてのリソースを解放します。  
  
##  <a name="delete"></a>CTokenGroups::Delete  
 削除、`CSid`とその関連付けられた属性から、`CTokenGroups`オブジェクトです。  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)のセキュリティ識別子 (SID) と属性が削除されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。 true の場合、`CSid`が削除され、false の場合それ以外の場合。  
  
##  <a name="deleteall"></a>CTokenGroups::DeleteAll  
 すべて削除`CSid`オブジェクトと、関連付けられた属性から、`CTokenGroups`オブジェクトです。  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>CTokenGroups::GetCount  
 数を返す`CSid`に含まれるオブジェクト`CTokenGroups`します。  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 数を返す[CSid](../../atl/reference/csid-class.md)オブジェクトとその関連の属性に含まれている、`CTokenGroups`オブジェクトです。  
  
##  <a name="getlength"></a>CTokenGroups::GetLength  
 サイズを返す、 **CTokenGroup**オブジェクトです。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>コメント  
 合計サイズを返す、 **CTokenGroup** (バイト単位) のオブジェクト。  
  
##  <a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS  
 ポインターを取得、 **TOKEN_GROUPS**構造体。  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを取得、 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)構造に属する、`CTokenGroups`アクセス トークンのオブジェクト。  
  
##  <a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes  
 取得、`CSid`オブジェクトと (必要に応じて) に属している属性、`CTokenGroups`オブジェクトです。  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSids`  
 配列を指すポインター [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `pAttributes`  
 Dword の配列へのポインター。 このパラメーターが省略されるか NULL の場合は、属性は取得されません。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、すべての列挙は、`CSid`に含まれるオブジェクト、`CTokenGroups`オブジェクト、および (必要に応じて) 属性のフラグに配列オブジェクト。  
  
##  <a name="lookupsid"></a>CTokenGroups::LookupSid  
 関連付けられている属性を取得、`CSid`オブジェクトです。  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `pdwAttributes`  
 そのまま使用する DWORD へのポインター、`CSid`オブジェクトの属性です。 省略するか NULL の場合、属性は取得されません。  
  
### <a name="return-value"></a>戻り値  
 返します。 true の場合、`CSid`が見つかると、false それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 設定`pdwAttributes`に NULL の存在を確認する方法を提供する、`CSid`属性にアクセスしなくてもします。 Windows 2000 上で正しくない結果が発生すると、アクセス権を確認するこのメソッドを使用しないことに注意してください。 アプリケーションが使用する代わりに、 [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership)メソッドです。  
  
##  <a name="operator_eq"></a>CTokenGroups::operator =  
 代入演算子。  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CTokenGroups`オブジェクトまたは[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)に割り当てる構造、`CTokenGroups`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CTokenGroups`オブジェクトです。  
  
##  <a name="operator_const_token_groups__star"></a>CTokenGroups::operator const TOKEN_GROUPS *  
 値へのポインターをキャスト、 **TOKEN_GROUPS**構造体。  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 値へのポインターをキャスト、 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)構造体。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [CSid クラス](../../atl/reference/csid-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

