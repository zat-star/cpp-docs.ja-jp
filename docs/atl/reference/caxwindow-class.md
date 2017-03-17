---
title: "CAxWindow クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
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
ms.openlocfilehash: 202c68fa4044a7c7a6c47c52b8095c5e7227b56d
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow-class"></a>CAxWindow クラス
このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[関連付け](#attachcontrol)|既存の ActiveX コントロールへのアタッチ、`CAxWindow`オブジェクトです。|  
|[CAxWindow](#caxwindow)|`CAxWindow` オブジェクトを構築します。|  
|[CreateControl](#createcontrol)|ActiveX コントロールを作成し、初期化して、し、ホストで、`CAxWindow`ウィンドウです。|  
|[CreateControlEx](#createcontrolex)|ActiveX コントロールを作成し、コントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[GetWndClassName](#getwndclassname)|(静的)定義済みのクラス名を取得、`CAxWindow`オブジェクトです。|  
|[QueryControl](#querycontrol)|取得、 **IUnknown**ホストされている ActiveX コントロールのです。|  
|[QueryHost](#queryhost)|取得、 **IUnknown**のポインター、`CAxWindow`オブジェクトです。|  
|[SetExternalDispatch](#setexternaldispatch)|によって使用される外部ディスパッチ インターフェイスの設定、`CAxWindow`オブジェクトです。|  
|[SetExternalUIHandler](#setexternaluihandler)|外部の設定**IDocHostUIHandler**によって使用されるインターフェイス、`CAxWindow`オブジェクトです。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|代入、 **HWND**既存**CAxWindow**オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 によって提供されるホスティング" **AtlAxWin80"**でラップされている`CAxWindow`します。  
  
 クラス`CAxWindow`の特殊な形式として実装された、`CAxWindowT`クラスです。 この特殊化は、としてを宣言されます。  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 使用することができます、基本クラスを変更する場合は、`CAxWindowT`し、テンプレート引数として新しい基本クラスを指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="attachcontrol"></a>CAxWindow::AttachControl  
 いずれかが既に存在しないし、ホストに指定したコントロールをアタッチする場合は、新しいホスト オブジェクトを作成します。  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 [in]ポインター、 **IUnknown**コントロールのです。  
  
 `ppUnkContainer`  
 [out]ポインター、 **IUnknown**ホストの (、 **AxWin**オブジェクト)。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 アタッチされるコントロール オブジェクトを呼び出す前に正しく初期化する必要があります`AttachControl`します。  
  
##  <a name="caxwindow"></a>CAxWindow::CAxWindow  
 構築、`CAxWindow`オブジェクトの既存のウィンドウ オブジェクトのハンドルを使用します。  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウ オブジェクトへのハンドル。  
  
##  <a name="createcontrol"></a>については  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  
```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールを作成するための文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。 Windows Mobile プラットフォームでは、ProgID と CLSID のみがサポートされています。 Windows CE には、プラットフォームが埋め込まれている、Windows Mobile のサポートが CE IE サポート以外、ProgID を含むすべての型 CLSID、URL、参照にアクティブだったドキュメントと HTML のフラグメントにします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 [out]受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
 `dwResID`  
 HTML のリソースのリソース ID です。 WebBrowser コントロールが作成され、指定されたリソースに読み込まれます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドの&2; 番目のバージョンが使用されている場合、HTML コントロールが作成され、によって識別されるリソースにバインドされている`dwResID`します。  
  
 このメソッドでは、呼び出しと同じ結果を提供します。  
  
 [!code-cpp[NVC_ATL_Windowing #&42;](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 参照してください[CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic)を作成するには、初期化、およびライセンスされた ActiveX コントロールをホストします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CreateControl`です。  
  
##  <a name="createcontrolex"></a>CAxWindow::CreateControlEx  
 ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  
```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 コントロールを作成するための文字列へのポインター。 次の方法のいずれかでフォーマットされている必要があります。  
  
-   ProgID など"MSCAL します。Calendar.7"  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"などの CLSID  
  
-   URL"http://www.microsoft.com"など  
  
-   などのアクティブなドキュメントへの参照"file://\\\Documents\MyDoc.doc"  
  
-   などの HTML のフラグメント"MSHTML:\<HTML >\<本文 > これは、行のテキスト\</body >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:"MSHTML ストリームとして指定できるように、HTML フラグメントを付ける必要があります。 Windows Mobile プラットフォームでは、ProgID と CLSID のみがサポートされています。 Windows CE には、プラットフォームが埋め込まれている、Windows Mobile のサポートが CE IE サポート以外、ProgID を含むすべての型 CLSID、URL、参照にアクティブだったドキュメントと HTML のフラグメントにします。  
  
 `pStream`  
 [in]コントロールのプロパティを初期化するために使用されるストリームへのポインター。 できる**NULL**します。  
  
 `ppUnkContainer`  
 [out]受け取るポインターのアドレス、 **IUnknown**のコンテナーです。 できる**NULL**します。  
  
 `ppUnkControl`  
 [out]受け取るポインターのアドレス、 **IUnknown**コントロールのです。 できる**NULL**します。  
  
 `iidSink`  
 [in]格納されているオブジェクトのアウトゴーイング インターフェイスのインターフェイス id です。 できる**iid_ に**します。  
  
 *punkSink*  
 [in]ポインター、 **IUnknown**で指定された格納されているオブジェクトの接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`します。  
  
 `dwResID`  
 [in]HTML のリソースのリソース ID です。 WebBrowser コントロールが作成され、指定されたリソースに読み込まれます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このメソッドは[については](#createcontrol)、そのメソッドとは異なり`CreateControlEx`新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
 参照してください[CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex)を作成するには、初期化、およびライセンスされた ActiveX コントロールをホストします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CreateControlEx`です。  
  
##  <a name="getwndclassname"></a>CAxWindow::GetWndClassName  
 ウィンドウ クラスの名前を取得します。  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>戻り値  
 ない ActiveX コントロールをホストできるウィンドウ クラスの名前を含む文字列へのポインター。  
  
##  <a name="operator_eq"></a>CAxWindow::operator =  
 代入、`HWND`既存`CAxWindow`オブジェクトです。  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 現在の `CAxWindow` オブジェクトへの参照を返します。  
  
##  <a name="querycontrol"></a>CAxWindow::QueryControl  
 ホストされるコントロールの指定されたインターフェイスを取得します。  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コントロールのインターフェイスの IID を指定します。  
  
 `ppUnk`  
 [out]コントロールのインターフェイスへのポインター。 このメソッドのテンプレートのバージョンで必要はありません参照 ID に関連付けられている uuid 型指定されたインターフェイスが渡されない限りです。  
  
 `Q`  
 [in]クエリ対象のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="queryhost"></a>CAxWindow::QueryHost  
 ホストの指定したインターフェイスを返します。  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]コントロールのインターフェイスの IID を指定します。  
  
 `ppUnk`  
 [out]ホスト上のインターフェイスへのポインター。 このメソッドのテンプレートのバージョンで必要はありません参照 ID に関連付けられている uuid 型指定されたインターフェイスが渡されない限りです。  
  
 `Q`  
 [in]クエリ対象のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ホストのインターフェイスによって実装される、ホスト ウィンドウのコードの基になる機能にアクセスを許可する**AxWin**します。  
  
##  <a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch  
 外部のディスパッチ インターフェイスを設定、`CAxWindow`オブジェクトです。  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler  
 外部の設定[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクトです。  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUIHandler*  
 [in]ポインター、 **IDocHostUIHandlerDispatch**インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 外部`IDocHostUIHandlerDispatch`インターフェイスがホストのサイトを照会するコントロールで使用される、`IDocHostUIHandlerDispatch`インターフェイスです。 WebBrowser コントロールはこれを行う&1; つのコントロールです。  
  
## <a name="see-also"></a>関連項目  
 [ATLCON サンプル](../../visual-cpp-samples.md)   
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [コントロール コンテインメントよく寄せられる質問](../../atl/atl-control-containment-faq.md)


