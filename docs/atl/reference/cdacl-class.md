---
title: "CDacl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
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
ms.openlocfilehash: bb418919c26e3c0054a151b859cdf3f31c5d73a8
ms.lasthandoff: 02/24/2017

---
# <a name="cdacl-class"></a>CDacl クラス
このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|コンストラクターです。|  
|[CDacl:: ~ CDacl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|許可されているように ACE を (アクセス制御エントリ) を追加、`CDacl`オブジェクトです。|  
|[CDacl::AddDeniedAce](#adddeniedace)|拒否 ACE を追加、`CDacl`オブジェクトです。|  
|[CDacl::GetAceCount](#getacecount)|Ace (アクセス制御エントリ) の数を返す、`CDacl`オブジェクトです。|  
|[CDacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) の削除、`CDacl`オブジェクトです。|  
|[CDacl::RemoveAllAces](#removeallaces)|すべてに含まれている Ace の削除、`CDacl`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 オブジェクトのセキュリティ記述子には、DACL を含めることができます。 DACL には、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する&0; 個以上の Ace (アクセス制御エントリ) が含まれています。 DACL が空の場合 (つまり、それに含まれる Ace が&0; 個)、アクセスが明示的に許可しないアクセスが暗黙的に拒否されるためです。 ただし、オブジェクトのセキュリティ記述子が DACL を持たない場合は、オブジェクトが保護されていない、完全なアクセス権を持つすべてのユーザー。  
  
 オブジェクトの DACL を取得するには、は、オブジェクトの所有者であるか、READ_CONTROL オブジェクトへのアクセスがある必要があります。 オブジェクトの DACL を変更するには、WRITE_DAC オブジェクトへのアクセスが必要です。  
  
 作成、追加、削除、およびから Ace を削除するクラスのメソッドを使用して、`CDacl`オブジェクトです。 関連項目[AtlGetDacl](http://msdn.microsoft.com/library/a0973648-0d46-4c1a-914f-bda861fe5d19)と[AtlSetDacl](http://msdn.microsoft.com/library/eb88ccb6-1f1b-444d-b0c9-8d5cd0dd6c0b)します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
 許可されているように ACE を (アクセス制御エントリ) を追加、`CDacl`オブジェクトです。  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md)オブジェクトです。  
  
 `AccessMask`  
 許可されるアクセス権のマスクを指定指定した`CSid`オブジェクトです。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**に ACE を追加する場合、`CDacl`オブジェクト、 **false**失敗します。  
  
### <a name="remarks"></a>コメント  
 A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する&0; 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを許可する ACE の追加、`CDacl`オブジェクトです。  
  
> [!NOTE]
>  2 番目の形式の`AddAllowedAce`のみ利用可能で、Windows 2000 でそれ以降。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
 拒否 ACE (アクセス制御エントリ) に追加、`CDacl`オブジェクトです。  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 `CSid` オブジェクト。  
  
 `AccessMask`  
 拒否するアクセス権のマスクを指定指定した`CSid`オブジェクトです。  
  
 `AceFlags`  
 ACE の継承を制御するビット フラグのセット。 既定値は、メソッドの最初の形式では 0 です。  
  
 `pObjectType`  
 オブジェクトの型。  
  
 `pInheritedObjectType`  
 継承されたオブジェクトの型。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**に ACE を追加する場合、`CDacl`オブジェクト、 **false**失敗します。  
  
### <a name="remarks"></a>コメント  
 A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する&0; 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを拒否する ACE を追加、`CDacl`オブジェクトです。  
  
> [!NOTE]
>  2 番目の形式の`AddDeniedAce`のみ利用可能で、Windows 2000 でそれ以降。  
  
 参照してください[ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919)で設定できるさまざまなフラグの詳細については、`AceFlags`パラメーター。  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 コンストラクターです。  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存の**ACL** (アクセス制御リスト) の構造体。  
  
### <a name="remarks"></a>コメント  
 `CDacl`オブジェクトを既存を使用して必要に応じて作成できる**ACL**構造体。 DACL (随意アクセス制御リスト) のみを確認することが重要と SACL ではありません (システム アクセス制御リスト) は、このパラメーターとして渡す必要があります。 デバッグ ビルドで、SACL を渡すことにより、アサートされます。 リリース ビルドでは、SACL を渡すことが発生 (アクセス制御エントリ) の Ace は無視され、ACL でしエラーは発生しません。  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 デストラクターです。  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターを使用してすべての Ace (アクセス制御エントリ) を含む、オブジェクトが取得したリソースを解放[CDacl::RemoveAllAces](#removeallaces)します。  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 Ace (アクセス制御エントリ) の数を返す、`CDacl`オブジェクトです。  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 含まれている Ace の数を返す、`CDacl`オブジェクトです。  
  
##  <a name="operator_eq"></a>CDacl::operator =  
 代入演算子。  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 既存のオブジェクトに割り当てられる ACL (アクセス制御リスト)。  
  
### <a name="return-value"></a>戻り値  
 更新されたへの参照を返します`CDacl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数には、DACL (随意アクセス制御リスト) を渡すだけことを確認してください。 SACL (システム アクセス制御リスト) を渡すことをこの関数によってアサート デバッグ ビルドでがエラーが発生しないリリース ビルドでします。  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 特定の ACE (アクセス制御エントリ) の削除、`CDacl`オブジェクトです。  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する ACE エントリのインデックスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 すべてに含まれている Ace (アクセス制御エントリ) の削除、`CDacl`オブジェクトです。  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>コメント  
 削除ごと**ACE** (アクセス制御エントリ) 構造体 (存在する場合) で、`CDacl`オブジェクトです。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [CAcl クラス](../../atl/reference/cacl-class.md)   
 [Acl](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)

