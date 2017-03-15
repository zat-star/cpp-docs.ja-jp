---
title: "CAcl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAcl
- ATL::CAcl
- ATLSECURITY/CAcl
- ATL.CAcl
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
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
ms.openlocfilehash: 52de083664c2e9ca00a140450cb43372aff28428
ms.lasthandoff: 02/24/2017

---
# <a name="cacl-class"></a>CAcl クラス
このクラスは、用のラッパー、 `ACL` (アクセス制御リスト) の構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|配列`ACCESS_MASK`秒です。|  
|[CAcl::CAceFlagArray](#caceflagarray)|配列`BYTE`秒です。|  
|[CAcl::CAceTypeArray](#cacetypearray)|配列`BYTE`秒です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|コンストラクターです。|  
|[CAcl:: ~ CAcl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|アクセス制御の数のエントリ (ACE) オブジェクトを返します。|  
|[CAcl::GetAclEntries](#getaclentries)|アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクトです。|  
|[CAcl::GetAclEntry](#getaclentry)|すべてのエントリに関する情報の取得、`CAcl`オブジェクトです。|  
|[CAcl::GetLength](#getlength)|ACL の長さを返します。|  
|[CAcl::GetPACL](#getpacl)|PACL (ACL へのポインター) を返します。|  
|[CAcl::IsEmpty](#isempty)|テスト、`CAcl`エントリのオブジェクト。|  
|[CAcl::IsNull](#isnull)|ステータスを返す、`CAcl`オブジェクトです。|  
|[CAcl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) の削除、`CAcl`オブジェクトです。|  
|[CAcl::RemoveAces](#removeaces)|すべての Ace (アクセス制御エントリ) を削除、`CAcl`に適用されている、指定された`CSid`します。|  
|[CAcl::SetEmpty](#setempty)|マーク、`CAcl`オブジェクト空として取得します。|  
|[CAcl::SetNull](#setnull)|マーク、`CAcl`オブジェクトとして`NULL`します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|キャスト、`CAcl`オブジェクトを`ACL`構造体。|  
|[CAcl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 **ACL**構造体は、ACL (アクセス制御リスト) のヘッダー。 ACL には、連続した&0; 個以上の一覧が含まれています。 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868) (アクセス制御エントリ)。 ACL 内の個々 の Ace の番号が 0 から*n-1*ここで、 *n* ACL 内の Ace の数です。 ACL を編集するには、アプリケーションは、インデックスを使用して ACL 内のアクセス制御エントリ (ACE) を参照します。  
  
 ACL の&2; 種類があります。  
  
-   随意  
  
-   システム  
  
 随意 ACL は、オブジェクトの所有者によって制御されますか、与えられたユーザー **WRITE_DAC**オブジェクトにアクセスします。 オブジェクトへのアクセスの特定のユーザーとグループを持てることを指定します。 たとえば、ファイルの所有者は、ことができますや、ファイルにアクセスされていないユーザーおよびグループを制御する随意 ACL を使用できます。  
  
 オブジェクトには、システム レベルのセキュリティ情報がシステムには、システム管理者によって制御される ACL の形式で、それに関連付けられていることもできます。 システムの ACL は、オブジェクトにアクセスするために、試行を監査するシステム管理者を許可できます。  
  
 詳細については、次を参照してください。、 [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872)の説明、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="a-namecaccessmaskarraya--caclcaccessmaskarray"></a><a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 ACCESS_MASK オブジェクトの配列。  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef では、アクセス制御エントリ (Ace) に使用されるアクセス権を格納するために使用する配列の型を指定します。  
  
##  <a name="a-namecaceflagarraya--caclcaceflagarray"></a><a name="caceflagarray"></a>CAcl::CAceFlagArray  
 バイト配列。  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef では、アクセス制御エントリ (ACE) の種類に固有の制御フラグを定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)可能なフラグの完全なリストの定義。  
  
##  <a name="a-namecacetypearraya--caclcacetypearray"></a><a name="cacetypearray"></a>CAcl::CAceTypeArray  
 バイト配列。  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>コメント  
 この typedef では、ACCESS_ALLOWED_ACE_TYPE や ACCESS_DENIED_ACE_TYPE などのアクセス制御エントリ (ACE) オブジェクトの種類を定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)使用可能な型の完全なリストの定義。  
  
##  <a name="a-namecacla--caclcacl"></a><a name="cacl"></a>CAcl::CAcl  
 コンストラクターです。  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の `CAcl` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CAcl`オブジェクトを既存を使用して必要に応じて作成できる`CAcl`オブジェクトです。  
  
##  <a name="a-namedtora--caclcacl"></a><a name="dtor"></a>CAcl:: ~ CAcl  
 デストラクターです。  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、オブジェクトで取得したリソースを解放します。  
  
##  <a name="a-namegetacecounta--caclgetacecount"></a><a name="getacecount"></a>CAcl::GetAceCount  
 アクセス制御の数のエントリ (ACE) オブジェクトを返します。  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ACE のエントリの数を返す、`CAcl`オブジェクトです。  
  
##  <a name="a-namegetaclentriesa--caclgetaclentries"></a><a name="getaclentries"></a>CAcl::GetAclEntries  
 アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクトです。  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSids`  
 配列へのポインター [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 *pAccessMasks*  
 アクセス マスク。  
  
 *pAceTypes*  
 アクセス制御エントリ ( **ACE**) の種類。  
  
 *pAceFlags*  
 **ACE**フラグ。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって、配列パラメーターの詳細をすべて**ACE**に含まれるオブジェクト、`CAcl`オブジェクトです。 その特定の配列の詳細については、必要がない場合は、NULL を使用します。  
  
 つまりの最初の要素の互いに、各配列の内容が対応、`CAccessMaskArray`の最初の要素に対応する配列、`CSidArray`配列型、およびなどです。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE 型とフラグの詳細についてです。  
  
##  <a name="a-namegetaclentrya--caclgetaclentry"></a><a name="getaclentry"></a>CAcl::GetAclEntry  
 すべてのアクセス制御リスト (ACL) 内のエントリに関する情報を取得します。  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 取得する ACL エントリのインデックスです。  
  
 `pSid`  
 [CSid](../../atl/reference/csid-class.md) ACL エントリを適用するオブジェクトします。  
  
 *pMask*  
 アクセス許可または拒否するアクセス許可を指定するマスク。  
  
 `pType`  
 ACE の型。  
  
 `pFlags`  
 ACE のフラグです。  
  
 `pObjectType`  
 オブジェクトの型。 オブジェクトの種類は、ACE で指定されていない場合、または ACE がオブジェクト ACE ではない場合 GUID_ に設定されます。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。 ACE がオブジェクト ACE ではない場合、ACE の継承されたオブジェクトの種類が指定されていない場合または GUID_ に設定されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドより多くの情報を提供する ACE ごとの情報をすべて取得は[CAcl::GetAclEntries](#getaclentries)単独で使用できるようにします。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE 型とフラグの詳細についてです。  
  
##  <a name="a-namegetlengtha--caclgetlength"></a><a name="getlength"></a>CAcl::GetLength  
 アクセス制御リスト (ACL) の長さを返します。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 必要な長さを保持するために必要なバイト数で返します、 **ACL**構造体。  
  
##  <a name="a-namegetpacla--caclgetpacl"></a><a name="getpacl"></a>CAcl::GetPACL  
 アクセス制御リスト (ACL) へのポインターを返します。  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、 **ACL**構造体。  
  
##  <a name="a-nameisemptya--caclisempty"></a><a name="isempty"></a>CAcl::IsEmpty  
 テスト、`CAcl`エントリのオブジェクト。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します。 **true**場合、`CAcl`オブジェクトが NULL でないと、エントリがありません。 返します。 **false**場合、`CAcl`オブジェクトが NULL であるか、または、少なくとも&1; つのエントリが含まれています。  
  
##  <a name="a-nameisnulla--caclisnull"></a><a name="isnull"></a>CAcl::IsNull  
 ステータスを返す、`CAcl`オブジェクトです。  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合、`CAcl`オブジェクトが NULL の場合、 **false**それ以外の場合。  
  
##  <a name="a-nameoperatorconstaclstara--cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a>CAcl::operator const ACL *  
 キャスト、`CAcl`オブジェクトを**ACL** (アクセス制御リスト) の構造体。  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>コメント  
 アドレスを返す、 **ACL**構造体。  
  
##  <a name="a-nameoperatoreqa--cacloperator-"></a><a name="operator_eq"></a>CAcl::operator =  
 代入演算子。  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CAcl`を既存のオブジェクトを割り当てる。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CAcl`オブジェクトです。  
  
##  <a name="a-nameremoveacea--caclremoveace"></a><a name="removeace"></a>CAcl::RemoveAce  
 特定の ACE (アクセス制御エントリ) の削除、 **CAcl**オブジェクトです。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。  
  
##  <a name="a-nameremoveacesa--caclremoveaces"></a><a name="removeaces"></a>CAcl::RemoveAces  
 Alls Ace (アクセス制御エントリ) を削除、`CAcl`に適用されている、指定された`CSid`します。  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 `CSid` オブジェクトへの参照。  
  
##  <a name="a-namesetemptya--caclsetempty"></a><a name="setempty"></a>CAcl::SetEmpty  
 マーク、`CAcl`オブジェクト空として取得します。  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAcl`空または NULL に設定できます。&2; つの状態は異なります。  
  
##  <a name="a-namesetnulla--caclsetnull"></a><a name="setnull"></a>CAcl::SetNull  
 マーク、`CAcl`として NULL オブジェクトです。  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAcl`空または NULL に設定できます。&2; つの状態は異なります。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

