---
title: "IObjectSafetyImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: cdcc008797e94988fb42fd6239603fa300a84233
ms.lasthandoff: 03/31/2017

---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl クラス
このクラスの既定の実装を提供する、`IObjectSafety`インターフェイスを取得し、オブジェクトの安全性レベルを設定するクライアントを許可します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IObjectSafetyImpl`です。  
  
 *dwSupportedSafety*  
 コントロールのサポートされている安全性のオプションを指定します。 次のいずれかの値になります。  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER**で識別されるインターフェイス、 [SetInterfaceSafetyOptions](#setinterfacesafetyoptions)パラメーター`riid`加える必要のあるスクリプトを実行します。  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA**で識別されるインターフェイス、`SetInterfaceSafetyOptions`パラメーター`riid`加える必要のある信頼されていないデータの安全な初期化中にします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|オブジェクトに現在設定安全性のオプションと同様に、オブジェクトでサポートされている安全性のオプションを取得します。|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|オブジェクトを初期化またはスクリプトに対して安全になります。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|オブジェクトの現在の安全性レベルを格納します。|  
  
## <a name="remarks"></a>コメント  
 クラス`IObjectSafetyImpl`の既定の実装を提供`IObjectSafety`です。 `IObjectSafety`インターフェイスにより、クライアントが取得され、オブジェクトの安全性レベルを設定します。 たとえば、web ブラウザーを呼び出すことができます**IObjectSafety::SetInterfaceSafetyOptions**初期化に対して安全またはスクリプトを実行して安全なコントロールを作成します。  
  
 使用して、 [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category)マクロを**CATID_SafeForScripting**と**CATID_SafeForInitializing**コンポーネントのカテゴリは、コンポーネントが安全でないことを指定する代替方法を提供します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 オブジェクトに現在設定安全性のオプションと同様に、オブジェクトでサポートされている安全性のオプションを取得します。  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>コメント  
 実装のオブジェクトの実装でサポートされている任意のインターフェイスの適切な値を返します**iunknown::queryinterface**です。  
  
> [!IMPORTANT]
>  サポートする任意のオブジェクト`IObjectSafety`に独自のセキュリティと任意のオブジェクトを代行させるを担当します。 プログラマ必要があります、ユーザーのコンテキストでのコードを実行する際に生じる問題を考慮、クロスサイト スクリプティングと適切なゾーン チェックを実行します。  
  
 参照してください[IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 オブジェクトの現在の安全性レベルを格納します。  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 により、オブジェクトを設定してスクリプトまたは初期化の安全な[m_dwCurrentSafety](#m_dwcurrentsafety)適切な値のメンバーです。  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>コメント  
 実装を返します**E_NOINTERFACE**のオブジェクトの実装でサポートされていない任意のインターフェイスの**iunknown::queryinterface**です。  
  
> [!IMPORTANT]
>  サポートする任意のオブジェクト`IObjectSafety`に独自のセキュリティと任意のオブジェクトを代行させるを担当します。 プログラマ必要があります、ユーザーのコンテキストでのコードを実行する際に生じる問題を考慮、クロスサイト スクリプティングと適切なゾーン チェックを実行します。  
  
 参照してください[IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IObjectSafety インターフェイス](https://msdn.microsoft.com/library/aa768224.aspx)   
 [クラスの概要](../../atl/atl-class-overview.md)

