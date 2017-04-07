---
title: "IAxWinHostWindow インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- No header/ATL::IAxWinHostWindow
- No header/ATL::AttachControl
- No header/ATL::CreateControl
- No header/ATL::CreateControlEx
- No header/ATL::QueryControl
- No header/ATL::SetExternalDispatch
- No header/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
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
ms.openlocfilehash: 6e366e7e30e7b4080462fbc21c29b4ecdf0214ae
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow インターフェイス
このインターフェイスは、コントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[関連付け](#attachcontrol)|既存のコントロールをそのホスト オブジェクトにアタッチします。|  
|[CreateControl](#createcontrol)|コントロールを作成し、そのホスト オブジェクトを結び付けます。|  
|[CreateControlEx](#createcontrolex)|コントロールを作成、ホスト オブジェクトにアタッチし、必要に応じて、イベント ハンドラーを設定します。|  
|[QueryControl](#querycontrol)|ホストされるコントロールのインターフェイス ポインターを返します。|  
|[SetExternalDispatch](#setexternaldispatch)|外部の設定`IDispatch`インターフェイスです。|  
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定`IDocHostUIHandlerDispatch`インターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、オブジェクトのホスト、ATL の ActiveX コントロールによって公開されます。 作成またはホストされるコントロールからインターフェイスを取得したり、Web ブラウザーをホストしているときに、外部のディスパッチ インターフェイスまたは使用するための UI ハンドラーを設定、ホスト オブジェクトへのコントロールをアタッチするには、このインターフェイスのメソッドを呼び出します。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のようとして idl ファイルまたは C++ では、使用可能です。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 識別されるウィンドウを使用して、そのホスト オブジェクトを既存の (および前に初期化された) のコントロールを結び付けます`hWnd`します。  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkControl*  
 [in]ポインター、 **IUnknown**そのホスト オブジェクトにアタッチされているコントロールのインターフェイスです。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="createcontrol"></a>については  
 コントロールを作成し、初期化してで識別されるウィンドウでホスト`hWnd`します。  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) CLSID、ProgID、URL、または生の HTML にすることができます (付けた**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このウィンドウは、メッセージは、コントロールに反映させることができますので、その他のコンテナーの機能が動作できるように、このインターフェイスを公開する、そのホスト オブジェクトをサブクラス化されます。  
  
 このメソッドを呼び出すには、[詳細](#createcontrolex)します。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)します。  
  
##  <a name="createcontrolex"></a>詳細  
 ActiveX コントロールを作成、初期化して、および指定したウィンドウでホスト[については](#createcontrol)です。  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) CLSID、ProgID、URL、または生の HTML にすることができます (付いて**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 できる**NULL**します。  
  
 `ppUnk`  
 [out]受け取るポインターのアドレス、 **IUnknown**に作成されたコントロールのインターフェイスです。 できる**NULL**します。  
  
 *riidAdvise*  
 [in]格納されているオブジェクトのアウトゴーイング インターフェイスのインターフェイス id です。 できる**iid_ に**します。  
  
 *punkAdvise*  
 [in]ポインター、 **IUnknown**で指定された格納されているオブジェクトの接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 異なり、`CreateControl`メソッド、`CreateControlEx`新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[呼び出し](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)します。  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 ホストされるコントロールによって提供される指定されたインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]要求されているコントロール上のインターフェイスの ID です。  
  
 `ppvObject`  
 [out]作成されたコントロールの指定されたインターフェイスを受け取るポインターのアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 格納されているコントロールを使用できる外部のディスパッチ インターフェイスの設定、 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md)メソッドです。  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 外部を設定するには、この関数を呼び出す[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクトです。  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、 **IDocHostUIHandlerDispatch**インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 この関数は、ホストのサイト (Web ブラウザー コントロールで) などのコントロールで使用、`IDocHostUIHandlerDispatch`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](http://msdn.microsoft.com/library/ad1f4f16-608d-4e96-8d30-04d4ca906a7b)










