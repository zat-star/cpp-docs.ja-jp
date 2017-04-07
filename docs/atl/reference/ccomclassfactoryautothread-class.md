---
title: "CComClassFactoryAutoThread クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
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
ms.openlocfilehash: fcc5671fc136b061bf3e8109999ac91d302d3d3b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread クラス
このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス、およびオブジェクトが複数のアパートメント内に作成することができます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
  
## <a name="remarks"></a>コメント  
 `CComClassFactoryAutoThread`ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)はオブジェクトを複数のアパートメント内で作成できるようにします。 このサポートを利用する、EXE モジュールから派生させる[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`、指定、 [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&9;](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外側の不明な使用する必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**します。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外は、 **NULL**、`riid`する必要があります**IID_IUnknown**します。  
  
 `ppvObj`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObj`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 モジュールから派生している場合[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)、`CreateInstance`最初に関連付けられているアパートメントでオブジェクトを作成するスレッドを選択します。  
  
##  <a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 インクリメントおよびデクリメント モジュールのロックを呼び出すことによってカウント**_Module::Lock**と**_Module::Unlock**、それぞれします。  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `fLock`  
 [in]場合**TRUE**ロック数がインクリメントされます。 それ以外の場合、ロック カウントがデクリメントします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 使用する場合`CComClassFactoryAutoThread`、 **_Module**通常のグローバル インスタンスを指す[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 呼び出す`LockServer`クライアントは、複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持できます。  
  
## <a name="see-also"></a>関連項目  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 クラス](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton クラス](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

