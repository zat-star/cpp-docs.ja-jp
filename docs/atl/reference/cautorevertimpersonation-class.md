---
title: "CAutoRevertImpersonation クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoRevertImpersonation
- CAutoRevertImpersonation
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f86f1e5067583b3c4c615c8ca3095e8b67b3fffe
ms.lasthandoff: 02/24/2017

---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation クラス
このクラスは、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトがスコープ外になったときに、この状態にします。  
  
## <a name="syntax"></a>構文  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|構築、`CAutoRevertImpersonation`オブジェクト|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|アクセス トークンの偽装復帰を自動化します。|  
|[CAutoRevertImpersonation::Detach](#detach)|自動偽装復帰をキャンセルします。|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|このオブジェクトに関連付けられている現在のトークン アクセスを取得します。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストについて説明し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。 これらのアクセス トークンを表すことが、`CAccessToken`クラスです。  
  
 アクセス トークンを偽装する必要があります。 必要に応じて、このクラスがありますが、アクセス トークンの偽装は実行されません。nonimpersonated 状態に自動バージョンの再設定のみを実行します。 これは、アクセス トークンの偽装にはいくつかの方法を実行できるためです。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="a-nameattacha--cautorevertimpersonationattach"></a><a name="attach"></a>CAutoRevertImpersonation::Attach  
 アクセス トークンの偽装復帰を自動化します。  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pAT`  
 アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻す  
  
### <a name="remarks"></a>コメント  
 このメソッドは、場合にのみ使用する必要があります、 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md)が NULL のオブジェクトが作成された`CAccessToken`ポインター、または[デタッチ](#detach)既に呼び出されています。 単純な状況では、このメソッドを使用する必要はありません。  
  
##  <a name="a-namecautorevertimpersonationa--cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 `CAutoRevertImpersonation` オブジェクトを構築します。  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pAT`  
 アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻します。  
  
### <a name="remarks"></a>コメント  
 アクセス トークンの実際の偽装を実行するとは別にから、可能であればの作成前に、`CAutoRevertImpersonation`オブジェクトです。 この権限借用は元に戻す自動的にすると、`CAutoRevertImpersonation`オブジェクトがスコープから外れます。  
  
##  <a name="a-namedtora--cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>コメント  
 有効に現在権限借用を元に戻します、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトの構築時、またはを通じて提供される、[アタッチ](#attach)メソッドです。 ない場合`CAccessToken`が関連付けられている場合、デストラクターも何も起こりません。  
  
##  <a name="a-namedetacha--cautorevertimpersonationdetach"></a><a name="detach"></a>CAutoRevertImpersonation::Detach  
 自動偽装復帰をキャンセルします。  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられていたのアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)、またはアソシエーションが存在しない場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 呼び出す**デタッチ**により、`CAutoRevertImpersonation`オブジェクトに対して有効で現在の偽装を元に戻すから、 [CAccessToken](../../atl/reference/caccesstoken-class.md)このオブジェクトに関連付けられているオブジェクト。 `CAutoRevertImpersonation`効果なしに破棄またはできる、同じまたは別に再関連付け`CAccessToken`オブジェクトを使用して[アタッチ](#attach)します。  
  
##  <a name="a-namegetaccesstokena--cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 このオブジェクトに関連付けられている現在のトークン アクセスを取得します。  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられていたのアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)、またはアソシエーションが存在しない場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 権限の借用のバージョンを再設定を含めるためにこのメソッドが呼び出された場合、`CAccessToken`オブジェクト、[デタッチ](#detach)メソッドを代わりに使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ATLSecurity サンプル](../../visual-cpp-samples.md)   
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [クラスの概要](../../atl/atl-class-overview.md)

