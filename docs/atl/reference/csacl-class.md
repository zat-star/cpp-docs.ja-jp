---
title: "CSacl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 50f10ab765648d4b587a941ccf24726b53f14c88
ms.lasthandoff: 02/24/2017

---
# <a name="csacl-class"></a>CSacl クラス
このクラスは、SACL (システム アクセス制御リスト) 構造体のラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|コンストラクターです。|  
|[CSacl:: ~ CSacl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|監査のアクセス制御エントリ (ACE) を追加する、`CSacl`オブジェクトです。|  
|[CSacl::GetAceCount](#getacecount)|アクセス制御エントリ (Ace) の数を取得、`CSacl`オブジェクトです。|  
|[CSacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) の削除、 **CSacl**オブジェクトです。|  
|[CSacl::RemoveAllAces](#removeallaces)|すべてに含まれている Ace の削除、`CSacl`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 SACL には、ドメイン コント ローラーのセキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 SACL がログ エントリへのアクセス試行が発生したドメイン コント ローラーでのみ、オブジェクトのレプリカが含まれているすべてのドメイン コント ローラーではなくを生成することに注意してください。  
  
 を設定またはオブジェクトのセキュリティ記述子の SACL を取得するには、スレッドを要求するアクセス トークンで SE_SECURITY_NAME 特権を有効にする必要があります。 Administrators グループはこの権限が既定では、与えられてを持ち、それを他のユーザーまたはグループに付与されることができます。 権限を持っている許可されただけではありませんが必要です: 反映するために特権セキュリティのアクセス トークンで有効化する特権によって定義された操作を実行する前にします。 モデルは、特定のシステム操作にのみ有効になり、不要になったときに、無効にするには特権を使用できます。 参照してください[AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8)と[AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547) SE_SECURITY_NAME を有効にする例です。  
  
 追加、削除、作成、およびから Ace を削除するクラスのメソッドを使用して、 **SACL**オブジェクトです。 関連項目[AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8)と[AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547)します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="addauditace"></a>CSacl::AddAuditAce  
 監査のアクセス制御エントリ (ACE) を追加する、`CSacl`オブジェクトです。  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `AccessMask`  
 監査するアクセス権のマスクを指定指定した`CSid`オブジェクトです。  
  
 `bSuccess`  
 許可されているアクセス試行を監査するかどうかを指定します。 監査を有効にします。 true の場合に、このフラグを設定します。それ以外の場合、false に設定します。  
  
 *bFailure*  
 拒否されたアクセス試行を監査するかどうかを指定します。 監査を有効にします。 true の場合に、このフラグを設定します。それ以外の場合、false に設定します。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**に ACE を追加する場合、`CSacl`オブジェクト、 **false**失敗します。  
  
### <a name="remarks"></a>コメント  
 A`CSacl`オブジェクトには、セキュリティ イベント ログに監査レコードが生成されるアクセスの種類を指定するアクセス制御エントリ (Ace) が含まれています。 このメソッドは、このようなするように ACE を追加、`CSacl`オブジェクトです。 2 番目の形式の`AddAuditAce`のみ利用可能で、Windows 2000 でそれ以降。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="csacl"></a>CSacl::CSacl  
 コンストラクターです。  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の**ACL** (アクセス制御リスト) の構造体。  
  
### <a name="remarks"></a>コメント  
 `CSacl`オブジェクトを既存を使用して必要に応じて作成できる**ACL**構造体。 このパラメーターは、システム アクセス制御リスト (SACL) と随意アクセス制御リスト (DACL) ではなくことを確認します。 DACL が指定した場合のデバッグ ビルドでは、アサーションが発生します。 リリース ビルドでは、DACL からすべてのエントリは無視されます。  
  
##  <a name="dtor"></a>CSacl:: ~ CSacl  
 デストラクターです。  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、すべてのアクセス制御エントリ (Ace) を含む、オブジェクトが取得したすべてのリソースを解放します。  
  
##  <a name="getacecount"></a>CSacl::GetAceCount  
 アクセス制御エントリ (Ace) の数を取得、`CSacl`オブジェクトです。  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 含まれている Ace の数を返す、`CSacl`オブジェクトです。  
  
##  <a name="operator_eq"></a>CSacl::operator =  
 代入演算子。  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 **ACL**を既存のオブジェクトを割り当てる (アクセス制御リスト)。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CSacl`オブジェクトです。 いることを確認、 **ACL**パラメーターは実際には、システム アクセス制御リスト (SACL) と随意アクセス制御リスト (DACL) ではなく。 アサーションが発生すると、デバッグ ビルドでは、リリース ビルドでは、 **ACL**パラメーターは無視されます。  
  
##  <a name="removeace"></a>CSacl::RemoveAce  
 特定の ACE (アクセス制御エントリ) の削除、 **CSacl**オブジェクトです。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。  
  
##  <a name="removeallaces"></a>CSacl::RemoveAllAces  
 すべてに含まれるアクセス制御エントリ (Ace) の削除、`CSacl`オブジェクトです。  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>コメント  
 削除ごと**ACE**構造体 (存在する場合)、`CSacl`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [CAcl クラス](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

