---
title: "IAxWinAmbientDispatch インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- No header/ATL::IAxWinAmbientDispatch
- No header/ATL::get_AllowContextMenu
- No header/ATL::get_AllowShowUI
- No header/ATL::get_AllowWindowlessActivation
- No header/ATL::get_BackColor
- No header/ATL::get_DisplayAsDefault
- No header/ATL::get_DocHostDoubleClickFlags
- No header/ATL::get_DocHostFlags
- No header/ATL::get_Font
- No header/ATL::get_ForeColor
- No header/ATL::get_LocaleID
- No header/ATL::get_MessageReflect
- No header/ATL::get_OptionKeyPath
- No header/ATL::get_ShowGrabHandles
- No header/ATL::get_ShowHatching
- No header/ATL::get_UserMode
- No header/ATL::put_AllowContextMenu
- No header/ATL::put_AllowShowUI
- No header/ATL::put_AllowWindowlessActivation
- No header/ATL::put_BackColor
- No header/ATL::put_DisplayAsDefault
- No header/ATL::put_DocHostDoubleClickFlags
- No header/ATL::put_DocHostFlags
- No header/ATL::put_Font
- No header/ATL::put_ForeColor
- No header/ATL::put_LocaleID
- No header/ATL::put_MessageReflect
- No header/ATL::put_OptionKeyPath
- No header/ATL::put_UserMode
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 2352b970c81f58d164fb47a6d7a4728c708d864a
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch インターフェイス
このインターフェイスは、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[get_BackColor](#get_backcolor)|`BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。|  
|[get_DisplayAsDefault](#get_displayasdefault)|**動作**アンビエント プロパティにより、既定のコントロールであるかどうかを確認するためのコントロールです。|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags**プロパティは、ダブルクリックに応答で実行される操作を指定します。|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags**プロパティは、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[get_Font](#get_font)|**フォント**プロパティは、コンテナーのアンビエント フォントを指定します。|  
|[get_ForeColor](#get_forecolor)|`ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。|  
|[get_LocaleID](#get_localeid)|**LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles**アンビエント プロパティでは、コントロールを調べるかどうかは、グラブ ハンドルを使った描画こと自体必要があります。|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching**アンビエント プロパティでは、コントロールを調べるかどうかハッチ自体を描画する必要があります。|  
|[get_UserMode](#get_usermode)|**UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[put_BackColor](#put_backcolor)|`BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。|  
|[put_DisplayAsDefault](#put_displayasdefault)|**動作**アンビエント プロパティにより、既定のコントロールであるかどうかを確認するためのコントロールです。|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags**プロパティは、ダブルクリックに応答で実行される操作を指定します。|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags**プロパティは、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[put_Font](#put_font)|**フォント**プロパティは、コンテナーのアンビエント フォントを指定します。|  
|[put_ForeColor](#put_forecolor)|`ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。|  
|[put_LocaleID](#put_localeid)|**LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。|  
|[put_UserMode](#put_usermode)|**UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、オブジェクトのホスト、ATL の ActiveX コントロールによって公開されます。 ホストされるコントロールに使用可能なアンビエント プロパティを設定するかをコンテナーの動作の他の側面を指定は、このインターフェイスのメソッドを呼び出します。 提供されるプロパティを補足するために`IAxWinAmbientDispatch`を使用して[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)します。  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)をに関する型情報を読み込んでみます`IAxWinAmbientDispatch`と`IAxWinAmbientDispatchEx`コードが含まれるタイプ ライブラリからです。  
  
 ATL90.dll にリンクしている場合は、 **AXHost**は DLL のタイプ ライブラリから型情報を読み込みます。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)詳細です。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次の表に示すようにさまざまな形式で使用できます。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C++|atliface.h (ATLBase.h にも含まれます)|  
  
##  <a name="get_allowcontextmenu"></a>IAxWinAmbientDispatch::get_AllowContextMenu  
 **ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowContextMenu*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_allowshowui"></a>IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowShowUI*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="get_allowwindowlessactivation"></a>IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowWindowless*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_backcolor"></a>IAxWinAmbientDispatch::get_BackColor  
 `BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBackground*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**COLOR_BTNFACE**または**COLOR_WINDOW** (かどうか、ホスト ウィンドウの親がダイアログ ボックスかによって) には、このプロパティの既定値として。  
  
##  <a name="get_displayasdefault"></a>IAxWinAmbientDispatch::get_DisplayAsDefault  
 **動作**アンビエント プロパティにより、既定のコントロールであるかどうかを確認するためのコントロールです。  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbDisplayAsDefault*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="get_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**プロパティは、ダブルクリックに応答で実行される操作を指定します。  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwDocHostDoubleClickFlags*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**DOCHOSTUIDBLCLK_DEFAULT**としてこのプロパティの既定値です。  
  
##  <a name="get_dochostflags"></a>IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags**プロパティは、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwDocHostFlags*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**DOCHOSTUIFLAG_NO3DBORDER**としてこのプロパティの既定値です。  
  
##  <a name="get_font"></a>IAxWinAmbientDispatch::get_Font  
 **フォント**プロパティは、コンテナーのアンビエント フォントを指定します。  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 [out]アドレス、**この**インターフェイス ポインターを使用してこのプロパティの現在の値を受信します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装は、このプロパティの既定値として既定の GUI フォントやシステム フォントを使用します。  
  
##  <a name="get_forecolor"></a>IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrForeground*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。  
  
##  <a name="get_localeid"></a>IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>パラメーター  
 *plcidLocaleID*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。  
  
 プログラムのロケール Id、コントロールで使用されている、この方法では、アンビエント LocalID を検出ことができます。 ロケール Id がわかれば、リソース ファイルまたはサテライト DLL からなどのロケール固有のキャプションを読み込むためのコード、エラー メッセージ テキストを呼び出すことができます。  
  
##  <a name="get_messagereflect"></a>IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbMessageReflect*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_optionkeypath"></a>IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrOptionKeyPath*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="get_showgrabhandles"></a>IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles**アンビエント プロパティでは、コントロールを調べるかどうかは、グラブ ハンドルを使った描画こと自体必要があります。  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbShowGrabHandles*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクト実装は、常に**VARIANT_FALSE**としてこのプロパティの値。  
  
##  <a name="get_showhatching"></a>IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching**アンビエント プロパティでは、コントロールを調べるかどうかハッチ自体を描画する必要があります。  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbShowHatching*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクト実装は、常に**VARIANT_FALSE**としてこのプロパティの値。  
  
##  <a name="get_usermode"></a>IAxWinAmbientDispatch::get_UserMode  
 **UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbUserMode*  
 [out]このプロパティの現在の値を受け取るように変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_allowcontextmenu"></a>IAxWinAmbientDispatch::put_AllowContextMenu  
 **ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowContextMenu*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_allowshowui"></a>IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowShowUI*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="put_allowwindowlessactivation"></a>IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowWindowless*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_backcolor"></a>IAxWinAmbientDispatch::put_BackColor  
 `BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBackground*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**COLOR_BTNFACE**または**COLOR_WINDOW** (かどうか、ホスト ウィンドウの親がダイアログ ボックスかによって) には、このプロパティの既定値として。  
  
##  <a name="put_displayasdefault"></a>IAxWinAmbientDispatch::put_DisplayAsDefault  
 **動作**アンビエント プロパティにより、既定のコントロールであるかどうかを確認するためのコントロールです。  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDisplayAsDefault`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="put_dochostdoubleclickflags"></a>IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**プロパティは、ダブルクリックに応答で実行される操作を指定します。  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDocHostDoubleClickFlags*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**DOCHOSTUIDBLCLK_DEFAULT**としてこのプロパティの既定値です。  
  
##  <a name="put_dochostflags"></a>IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags**プロパティは、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDocHostFlags*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して**DOCHOSTUIFLAG_NO3DBORDER**としてこのプロパティの既定値です。  
  
##  <a name="put_font"></a>IAxWinAmbientDispatch::put_Font  
 **フォント**プロパティは、コンテナーのアンビエント フォントを指定します。  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装は、このプロパティの既定値として既定の GUI フォントやシステム フォントを使用します。  
  
##  <a name="put_forecolor"></a>IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrForeground*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。  
  
##  <a name="put_localeid"></a>IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lcidLocaleID*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。  
  
##  <a name="put_messagereflect"></a>IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 `bMessageReflect`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_optionkeypath"></a>IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrOptionKeyPath*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="put_usermode"></a>IAxWinAmbientDispatch::put_UserMode  
 **UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUserMode`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatchEx インターフェイス](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow インターフェイス](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](http://msdn.microsoft.com/library/ad1f4f16-608d-4e96-8d30-04d4ca906a7b)










