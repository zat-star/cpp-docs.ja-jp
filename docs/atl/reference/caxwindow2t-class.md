---
title: "CAxWindow2T クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAxWindow2T<TBase>
- ATL::CAxWindow2T
- CAxWindow2T
- ATL.CAxWindow2T<TBase>
- ATL.CAxWindow2T
- CAxWindow2
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: deed13f7e44246eca1e9d3d138f73d0f540dc0b1
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow2t-class"></a>CAxWindow2T クラス
このクラスは、ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートもありますウィンドウを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>パラメーター  
 *TBase*  
 元のクラス`CAxWindowT`派生します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|ホスト ウィンドウを作成します。|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|ウィンドウ クラスの名前を取得する静的メソッド。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|代入、`HWND`既存`CAxWindow2T`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CAxWindow2T`ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 `CAxWindow2T`ライセンスされた ActiveX コントロールをホストするためのサポートもあります。 によって提供されるホスティング" **AtlAxWinLic80**"でラップされている`CAxWindow2T`します。  
  
 クラス`CAxWindow2`の特殊な形式として実装された、`CAxWindow2T`クラスです。 この特殊化は、としてを宣言されます。  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`下にあるメンバーが記載されている[CAxWindow](../../atl/reference/caxwindow-class.md)します。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)のこのクラスのメンバーを使用するサンプルです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="a-namecaxwindow2ta--caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 `CAxWindow2T` オブジェクトを構築します。  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウのハンドル。  
  
##  <a name="a-namecreatea--caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::Create  
 ホスト ウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>コメント  
 `CAxWindow2T::Create`呼び出し[CWindow::Create](../../atl/reference/cwindow-class.md#create)で、`LPCTSTR``lpstrWndClass`パラメーター コントロールのホストを提供する、ウィンドウ クラスを設定する ( **AtlAxWinLic80**)。  
  
 参照してください`CWindow::Create`パラメーターと戻り値の詳細についてです。  
  
 **注**の値として 0 が使用する場合、`MenuOrID`パラメーター 0 u として指定する必要があります (既定値) コンパイラのエラーを回避します。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::Create`です。  
  
##  <a name="a-namecreatecontrollica--caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLicKey`  
 コントロールのライセンス キーライセンスの付いていないコントロールを作成する場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 参照してください[については](../../atl/reference/caxwindow-class.md#createcontrol)残りのパラメーターと戻り値の詳細についてです。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::CreateControlLic`です。  
  
##  <a name="a-namecreatecontrollicexa--caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLicKey`  
 コントロールのライセンス キーライセンスの付いていないコントロールを作成する場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 参照してください[CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex)残りのパラメーターと戻り値の詳細についてです。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::CreateControlLicEx`です。  
  
##  <a name="a-namegetwndclassnamea--caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 ウィンドウ クラスの名前を取得します。  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ クラスの名前を含む文字列へのポインター ( **AtlAxWinLic80**) ライセンスおよびライセンスの付いていない ActiveX コントロールをホストすることができます。  
  
##  <a name="a-nameoperatoreqa--caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::operator =  
 代入、`HWND`既存`CAxWindow2T`オブジェクトです。  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウのハンドル。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [コントロール コンテインメントよく寄せられる質問](../../atl/atl-control-containment-faq.md)

