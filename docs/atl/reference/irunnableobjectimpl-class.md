---
title: "IRunnableObjectImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a9b2698c195ac5bd709e6d40d3c30008d3fa26d4
ms.lasthandoff: 02/24/2017

---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IRunnableObjectImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|実行中のコントロールの CLSID が返されます。 ATL の実装では、CLSID を設定`GUID_NULL`返します**E_UNEXPECTED**します。|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|コントロールが実行されているかどうかを判断します。 ATL の実装を返します**TRUE**します。|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|実行中の状態には、コントロールをロックします。 ATL の実装を返します`S_OK`します。|  
|[IRunnableObjectImpl::Run](#run)|そのコントロールが実行を強制します。 ATL の実装を返します`S_OK`します。|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|コントロールが埋め込まれていることを示します。 ATL の実装を返します`S_OK`します。|  
  
## <a name="remarks"></a>コメント  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)インターフェイスは、コントロールが実行されているかどうかで、次の実行、または実行中の状態にロックするように強制するためのコンテナーを使用します。 クラス`IRunnableObjectImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-namegetrunningclassa--irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 実行中のコントロールの CLSID が返されます。  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装設定\* *lpClsid*に`GUID_NULL`返します**E_UNEXPECTED**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisrunninga--irunnableobjectimplisrunning"></a><a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 コントロールが実行されているかどうかを判断します。  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します**TRUE**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namelockrunninga--irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 実行中の状態には、コントロールをロックします。  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameruna--irunnableobjectimplrun"></a><a name="run"></a>IRunnableObjectImpl::Run  
 そのコントロールが実行を強制します。  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetcontainedobjecta--irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 コントロールが埋め込まれていることを示します。  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

