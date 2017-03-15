---
title: "クラスのされます |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATL::IDispEventSimpleImpl
- ATL.IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b7bc2c64139726f84f1c19c7d6b40e8d68cdc18
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventsimpleimpl-class"></a>されますクラス
このクラスの実装を提供する、`IDispatch`メソッドは、タイプ ライブラリから型情報を取得せずします。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。 `IDispEventSimpleImpl`基本クラスは、複合コントロールの場合は、このパラメーターの目的のコンテナー内のコントロールのリソース ID を使用します。 それ以外の場合では、任意の正の整数を使用します。  
  
 `T`  
 ユーザーのクラスから派生した`IDispEventSimpleImpl`します。  
  
 `pdiid`  
 このクラスで実装するイベントのディスパッチ インターフェイスの IID へのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|既定のイベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|イベント ソースとの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|イベント ソースとの接続が中断されます。|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|返します。 **E_NOTIMPL**します。|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|返します。 **E_NOTIMPL**します。|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|返します。 **E_NOTIMPL**します。|  
|[IDispEventSimpleImpl::Invoke](#invoke)|イベント ハンドラーを呼び出しますが、イベント シンク マップに一覧表示されます。|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|既定のイベント ソースとの接続が中断されます。|  
  
## <a name="remarks"></a>コメント  
 `IDispEventSimpleImpl`そのインターフェイスのメソッドとイベントは、すべての実装コードを提供するには、しなくても、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventSimpleImpl`実装を提供、`IDispatch`メソッドです。 処理にしているイベントの実装を指定する必要があるだけです。  
  
 `IDispEventSimpleImpl`組み合わせて動作、[イベント シンク マップ](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f)で、クラスで、適切なハンドラー関数にイベントをルーティングします。 このクラスを使用します。  
  
-   追加、 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)マクロを処理する各オブジェクト上の各イベントのイベント シンク マップします。  
  
-   ポインターを渡すことによって、各イベントの種類の情報を指定する[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)の各エントリにパラメーターとして構造体。 X86 で、プラットフォーム、`_ATL_FUNC_INFO.cc`値は CC_CDECL を持つ _ _stdcall のメソッドを呼び出すコールバック関数にする必要があります。  
  
-   呼び出す[DispEventAdvise](#dispeventadvise)基本クラスとソース オブジェクトの間の接続を確立します。  
  
-   呼び出す[DispEventUnadvise](#dispeventunadvise)結合を解除します。  
  
 派生する必要があります`IDispEventSimpleImpl`(に一意の値を使用して`nID`) の各オブジェクトのイベントを処理する必要があります。 別のソース オブジェクトに対してことを通知し、1 つのソース オブジェクトに対してアドバイズによって、基本クラスを再利用できますが、一度に&1; つのオブジェクトで処理できるソース オブジェクトの最大数が数によって制限される`IDispEventSimpleImpl`基本クラスです。  
  
 **IDispEventSimplImpl**と同じ機能を提供[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)、タイプ ライブラリからインターフェイスに関する型情報を取得しません。 のみに基づくコードが生成`IDispEventImpl`を使用することができますが、`IDispEventSimpleImpl`のコードを手動で追加しています。 使用する`IDispEventSimpleImpl`としないイベント インターフェイスを記述するタイプ ライブラリまたはしたタイプ ライブラリの使用に関連するオーバーヘッドを回避します。  
  
> [!NOTE]
> `IDispEventImpl``IDispEventSimpleImpl`の独自の実装を提供**:queryinterface**それぞれを有効にする`IDispEventImpl`または`IDispEventSimpleImpl`基本クラスが、メインの COM オブジェクトにクラス メンバーへの直接のアクセスを許可する時に別の COM id として機能します。  
  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
 詳細については、次を参照してください。[をサポートする IDispEventImpl](../../atl/supporting-idispeventimpl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-nameadvisea--idispeventsimpleimpladvise"></a><a name="advise"></a>IDispEventSimpleImpl::Advise  
 によって表されるイベント ソースに接続を確立するには、このメソッドを呼び出す*pUnk*します。  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`または、どのような障害`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 イベントが発生した接続が確立されると、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスの呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Advise`接続を確立によって決定されるオブジェクトの既定のイベント ソースの IID を取得して既定のイベント ソースと[AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155)します。  
  
##  <a name="a-namedispeventadvisea--idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise  
 によって表されるイベント ソースに接続を確立するには、このメソッドを呼び出す*pUnk*します。  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
 `piid`  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`または、どのような障害`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 イベントが発生した後で、 *pUnk*イベント シンク マップを使用して、クラス内のハンドラーにルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスの呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise`指定されたイベント ソースとの接続を確立`pdiid`します。  
  
##  <a name="a-namedispeventunadvisea--idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise  
 によって表されるイベント ソースに、接続が切断*pUnk*します。  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
 `piid`  
 イベント ソース オブジェクトの IID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`または、どのような障害`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 接続が切断された後、イベント シンク マップに表示されるハンドラー関数に不要になったイベントがルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスの呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `DispEventAdvise`指定されたイベント ソースによって確立された接続が切断`pdiid`します。  
  
##  <a name="a-namegetidsofnamesa--idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
 この実装の**IDispatch::GetIDsOfNames**返します**E_NOTIMPL**します。  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegettypeinfoa--idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 この実装の**が**返します**E_NOTIMPL**します。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[が](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegettypeinfocounta--idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 この実装の**IDispatch::GetTypeInfoCount**返します**E_NOTIMPL**します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinvokea--idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDispEventSimpleImpl::Invoke  
 この実装の**idispatch::invoke**イベント シンク マップに示されたイベント ハンドラーの呼び出しです。  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)します。  
  
##  <a name="a-nameunadvisea--idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispEventSimpleImpl::Unadvise  
 によって表されるイベント ソースに、接続が切断*pUnk*します。  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**イベント ソース オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`または、どのような障害`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 接続が切断された後、イベント シンク マップに表示されるハンドラー関数に不要になったイベントがルーティングされます。  
  
> [!NOTE]
>  複数のクラスが派生している場合`IDispEventSimpleImpl`クラス、興味のある特定の基本クラスの呼び出しのスコープでこのメソッドの呼び出しを明確に区別する必要があります。  
  
 `Unadvise`指定された既定のイベント ソースによって確立された接続が切断`pdiid`します。  
  
 **Unavise**によって決定されるオブジェクトの既定のイベント ソースの IID を取得して、既定のイベント ソースとの接続を区切り[AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155)します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl クラス](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [クラスの概要](../../atl/atl-class-overview.md)

