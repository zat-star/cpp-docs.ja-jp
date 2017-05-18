---
title: "IDispatchImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fff4cbc0a3f87b584f1a4211f4aad37228ed4da7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="idispatchimpl-class"></a>IDispatchImpl クラス
既定の実装を提供、`IDispatch`デュアル インターフェイスの一部です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `T`  
 デュアル インターフェイスです。  
  
 [入力] `piid`  
 IID へのポインター`T`します。  
  
 [入力] `plibid`  
 インターフェイスに関する情報を格納するタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。  
  
 [入力] `wMajor`  
 タイプ ライブラリのメジャー バージョン。 既定では、値は 1 です。  
  
 [入力] `wMinor`  
 タイプ ライブラリのマイナー バージョン。 既定では、値は 0 です。  
  
 [入力] `tihclass`  
 型情報の管理に使用されるクラス`T`します。 既定では、値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理する、プロテクト メンバー変数にします。 このデストラクターは `Release` を呼び出します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|一連の名前を対応する一連のディスパッチ識別子に割り当てます。|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|デュアル インターフェイスの型情報を取得します。|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|デュアル インターフェイスの使用可能な型情報があるかどうかを決定します。|  
|[IDispatchImpl::Invoke](#invoke)|メソッドとデュアル インターフェイスによって公開されるプロパティにアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 `IDispatchImpl`既定の実装を提供、`IDispatch`オブジェクトのデュアル インターフェイスの一部です。 デュアル インターフェイス`IDispatch`オートメーション互換型のみを使用しています。 ディスパッチのように、デュアル インターフェイスでは、事前バインディングと遅延バインディングがサポートしていますただし、デュアル インターフェイスは、vtable バインドもサポートします。  
  
 次の例では、一般的な実装の`IDispatchImpl`です。  
  
 [!code-cpp[NVC_ATL_COM&#47;](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 既定では、`IDispatchImpl`クラスの型情報を検索`T`レジストリにします。 登録されていないインターフェイスを実装するのに使用することができます、`IDispatchImpl`クラス定義済みのバージョン番号を使用して、レジストリへのアクセスがない場合。 作成する場合、`IDispatchImpl`オブジェクトの値として 0 xffff を持つ`wMajor`からの値として 0 xffff `wMinor`、`IDispatchImpl`クラスは、レジストリではなく、.dll ファイルからタイプ ライブラリを取得します。  
  
 `IDispatchImpl`型の静的メンバーを含む`CComTypeInfoHolder`デュアル インターフェイスの型情報を管理します。 同じデュアルを実装する複数のオブジェクトがある場合、インターフェイスのインスタンスを&1; つだけ`CComTypeInfoHolder`を使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames  
 一連の名前を対応する一連のディスパッチ識別子に割り当てます。  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo  
 デュアル インターフェイスの型情報を取得します。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[が](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount  
 デュアル インターフェイスの使用可能な型情報があるかどうかを決定します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>コメント  
 See `IDispatch::GetTypeInfoCount` in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl  
 コンストラクターです。 呼び出し`AddRef`デュアル インターフェイスの型情報を管理する、プロテクト メンバー変数にします。 デストラクターの呼び出し**リリース**します。  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>IDispatchImpl::Invoke  
 メソッドとデュアル インターフェイスによって公開されるプロパティにアクセスを提供します。  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

