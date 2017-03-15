---
title: "IDispEventImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 235955f8573ae7e430be3de2a96efdd7496d15de
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventimpl-class"></a>IDispEventImpl クラス
このクラスの実装を提供する、`IDispatch`メソッドです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。 `IDispEventImpl`基本クラスは、複合コントロールの場合は、このパラメーターの目的のコンテナー内のコントロールのリソース ID を使用します。 それ以外の場合では、任意の正の整数を使用します。  
  
 `T`  
 ユーザーのクラスから派生した`IDispEventImpl`します。  
  
 `pdiid`  
 このクラスで実装するイベントのディスパッチ インターフェイスの IID へのポインター。 表されるタイプ ライブラリのこのインターフェイスを定義する必要が`plibid`、 `wMajor`、および`wMinor`です。  
  
 `plibid`  
 ディスパッチ インターフェイスを定義するタイプ ライブラリへのポインターが指す`pdiid`します。 場合**>/documents/report1.rdl」の GUID_**イベントのソース オブジェクトからタイプ ライブラリが読み込まれます。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョン。 既定値は 0 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョン。 既定値は 0 です。  
  
 `tihclass`  
 型情報の管理に使用されるクラス`T`します。 既定値は型のクラス`CComTypeInfoHolder`。 ただし、このテンプレート パラメーター以外の型のクラスを提供することによりオーバーライドできます`CComTypeInfoHolder`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|型情報を管理するために使用するクラスです。 既定では、`CComTypeInfoHolder`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|指定したディスパッチ識別子の関数のインデックスを検索します。|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|対応する整数 Dispid 群に&1; つのメンバーおよびオプションの引数の名前のセットをマップします。|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|オブジェクトの型情報を取得します。|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|型情報インターフェイスの数を取得します。|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|ユーザー定義型の基本の種類を取得します。|  
  
## <a name="remarks"></a>コメント  
 `IDispEventImpl`そのインターフェイスのメソッドとイベントは、すべての実装コードを提供するには、しなくても、イベントのディスパッチ インターフェイスを実装する方法を提供します。 `IDispEventImpl`実装を提供、`IDispatch`メソッドです。 処理にしているイベントの実装を指定する必要があるだけです。  
  
 `IDispEventImpl`組み合わせて動作、[イベント シンク マップ](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f)で、クラスで、適切なハンドラー関数にイベントをルーティングします。 このクラスを使用します。  
  

 追加、 [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5)または[SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac)マクロを処理する各オブジェクト上の各イベントのイベント シンク マップします。 使用する場合`IDispEventImpl`複合コントロールの基本クラスを呼び出すこともできます[AtlAdviseSinkMap](http://msdn.microsoft.com/library/0757a6af-3de3-4179-8b4f-ccd137d919b4)を設定し、イベント シンク マップのすべてのエントリのイベント ソースとの接続を解除します。 それ以外の場合で、またはより細かく制御できる呼び出して[DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise)基本クラスとソース オブジェクトの間の接続を確立するためにします。 呼び出す[DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)結合を解除します。  

  
 派生する必要があります`IDispEventImpl`(に一意の値を使用して`nID`) の各オブジェクトのイベントを処理する必要があります。 別のソース オブジェクトに対してことを通知し、1 つのソース オブジェクトに対してアドバイズによって、基本クラスを再利用できますが、一度に&1; つのオブジェクトで処理できるソース オブジェクトの最大数が数によって制限される`IDispEventImpl`基本クラスです。  
  
 `IDispEventImpl`同じ機能を提供[されます](../../atl/reference/idispeventsimpleimpl-class.md)へのポインターとして指定して発生するのではなく、タイプ ライブラリからインターフェイスに関する型情報を取得してを除き、 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)構造体。 使用`IDispEventSimpleImpl`ときに、イベント インターフェイスを記述するタイプ ライブラリがあるまたはしないタイプ ライブラリの使用に関連するオーバーヘッドを回避します。  
  
> [!NOTE]
> `IDispEventImpl``IDispEventSimpleImpl`の独自の実装を提供**:queryinterface**それぞれを有効にする`IDispEventImpl`と`IDispEventSimpleImpl`基本クラスが、メインの COM オブジェクトにクラス メンバーへの直接のアクセスを許可する時に別の COM id として機能します。  
  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
 詳細については、次を参照してください。[をサポートする IDispEventImpl](../../atl/supporting-idispeventimpl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [されます](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namegetfuncinfofromida--idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 指定したディスパッチ識別子の関数のインデックスを検索します。  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]関数の ID への参照。  
  
 *dispidMember*  
 [in]関数のディスパッチの ID。  
  
 `lcid`  
 [in]関数の ID のロケール コンテキスト  
  
 `info`  
 [in]関数の呼び出し方法を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namegetidsofnamesa--idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 1 つのメンバーおよびオプションの引数の名前のセットに対応する整数への後続の呼び出しで使用できる Dispid セットを対応付けます[idispatch::invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)します。  
  
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
  
##  <a name="a-namegettypeinfoa--idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 オブジェクトの型情報を取得します。この型情報を使用して、インターフェイスの型情報を取得できます。  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegettypeinfocounta--idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 オブジェクトが提供する型情報インターフェイスの数 (0 または 1) を取得します。  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetuserdefinedtypea--idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 ユーザー定義型の基本の種類を取得します。  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTI`  
 [in]ポインター、 [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680)ユーザー定義型を含むインターフェイス。  
  
 *hrt*  
 [in]取得する型の説明へのハンドル。  
  
### <a name="return-value"></a>戻り値  
 バリアント型の型。  
  
### <a name="remarks"></a>コメント  
 参照してください[ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00)します。  
  
##  <a name="a-nameidispeventimpla--idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 コンストラクターです。 クラス テンプレート パラメーターの値を格納`plibid`、 `pdiid`、 `wMajor`、および`wMinor`です。  
  
```
IDispEventImpl();
```  
  
##  <a name="a-nametihclassa--idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass  
 この typedef クラス テンプレート パラメーターのインスタンスである`tihclass`です。  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>コメント  
 クラスは、既定では、`CComTypeInfoHolder`です。 `CComTypeInfoHolder`クラスの型情報を管理します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_FUNC_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [されますクラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5)   
 [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [クラスの概要](../../atl/atl-class-overview.md)
