---
title: "CComControlBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 988528a3658dee930df2cac6fd1a4add87302509
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrolbase-class"></a>CComControlBase クラス
このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|場合は、オーバーライド、`m_nAppearance`ストック プロパティは、型の`short`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|コンストラクターです。|  
|[CComControlBase:: ~ CComControlBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブにするか (`iVerb`と等しい`OLEIVERB_UIACTIVATE`)、ユーザー コントロールをダブルクリックしたときの動作を定義 ( `iVerb` equals `OLEIVERB_PRIMARY`)、コントロールが表示されます (`iVerb`と等しい`OLEIVERB_SHOW`)、またはコントロールをアクティブ化 (`iVerb`と等しい**OLEIVERB_INPLACEACTIVATE**)。|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブ化してを返します**TRUE**します。|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|コントロールのプロパティ ページを表示します。|  
|[CComControlBase::FireViewChange](#fireviewchange)|コントロールを再描画するためのコンテナーを確認するには、このメソッドを呼び出すか、コントロールのビューが変更された登録済みアドバイズ シンクに通知します。|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|取得**を示す**、現在の外観をコントロールの設定: フラット 3 d 1 の場合は 0 です。|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|取得**DISPID_AMBIENT_AUTOCLIP**コンテナーがコントロールの表示領域の自動クリップをサポートしているかどうかを示しますフラグ。|  
|[用意されています](#getambientbackcolor)|取得**DISPID_AMBIENT_BACKCOLOR**、コンテナーによって定義されたすべてのコントロールのアンビエント背景色。|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|取得**DISPID_AMBIENT_CHARSET**、コンテナーによって定義されたすべてのコントロールの周囲の文字セットします。|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|取得**ことにあります**、コンテナーによって定義されたすべてのコントロールの周囲の文字セットします。|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|取得**DISPID_AMBIENT_DISPLAYASDEFAULT**、あるフラグ**TRUE**かどうか、コンテナーが既定のボタンでは、このサイトのコントロールをマーク、したがってボタン コントロールが作成されます自体が太くフレームを使用しています。|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|取得**DISPID_AMBIENT_DISPLAYNAME**コンテナーがコントロールに指定された名前です。|  
|[CComControlBase::GetAmbientFont](#getambientfont)|取得、コンテナーへのポインターのアンビエント`IFont`インターフェイスです。|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|取得、コンテナーへのポインターのアンビエント**この**ディスパッチ インターフェイスです。|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|取得**DISPID_AMBIENT_FORECOLOR**、コンテナーによって定義されたすべてのコントロールのアンビエント前景色。|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|取得**DISPID_AMBIENT_LOCALEID**、コンテナーによって使用される言語の識別子。|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|取得**DISPID_AMBIENT_MESSAGEREFLECT**コンテナーは、ウィンドウ メッセージを受信するかどうかを示すフラグ (よう`WM_DRAWITEM`) イベントとして。|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|取得**DISPID_AMBIENT_PALETTE**コンテナーのアクセスに使用される、`HPALETTE`です。|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|指定されたコンテナーのプロパティを取得`id`します。|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|取得**DISPID_AMBIENT_RIGHTTOLEFT**方向がコンテナーによってコンテンツが表示されます。|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|取得**DISPID_AMBIENT_SCALEUNITS**コンテナーのアンビエント単位 (インチやセンチメートル) ラベルが表示されます。|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|取得**DISPID_AMBIENT_SHOWGRABHANDLES**コンテナーがアクティブなときにグラブ ハンドルを表示するコントロールを許可するかどうかを示すフラグ。|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|取得**DISPID_AMBIENT_SHOWHATCHING**コンテナーが UI がアクティブなハッチ パターンではそれ自体を表示するコントロールを許可するかどうかを示すフラグ。|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|取得**DISPID_AMBIENT_SUPPORTSMNEMONICS**コンテナーがニーモニックをサポートしているかどうかを示しますフラグ。|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|取得**DISPID_AMBIENT_TEXTALIGN**コンテナーが希望するテキストの配置: 一般的な配置 (数値、テキストを左) の場合は 0、左揃えの場合は 1、中央揃えの場合は 2 および 3 は右揃えにします。|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|取得**DISPID_AMBIENT_TOPTOBOTTOM**方向がコンテナーによってコンテンツが表示されます。|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|取得**DISPID_AMBIENT_UIDEAD**ユーザー インターフェイスの動作に対応するコントロールがあるかどうかを示しますフラグ。|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|取得**DISPID_AMBIENT_USERMODE**、コンテナーが実行モードであるかどうかを示すフラグ ( **TRUE**) またはデザイン モード ( **FALSE**)。|  
|[CComControlBase::GetDirty](#getdirty)|データ メンバーの値を返します`m_bRequiresSave`します。|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|X と y を取得、分子と倍率の分母の値の有効なコントロールの埋め込み先編集します。|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|どのステート内の動詞を非アクティブ状態から移行するコントロールをさせます`iVerb`ことを示します。|  
|[CComControlBase::InternalGetSite](#internalgetsite)|識別されたインターフェイスへのポインターのコントロールのサイトを照会するには、このメソッドを呼び出します。|  
|[CComControlBase::OnDraw](#ondraw)|コントロールを描画するには、このメソッドをオーバーライドします。|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|既定値**してから**描画に正規化デバイス コンテキストを準備し、コントロール クラスを呼び出し、`OnDraw`メソッドです。|  
|[CComControlBase::OnKillFocus](#onkillfocus)|コントロール、インプレース アクティブと有効なコントロール サイトを持つそのが、コントロールがフォーカスを失ったことをコンテナーに通知を確認します。|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|UI がユーザー モードにし、コントロールをアクティブ化を確認します。|  
|[CComControlBase::OnPaint](#onpaint)|描画するため、コンテナーを準備し、コントロールのクライアント領域の取得、コントロール クラスの`OnDraw`メソッドです。|  
|[CComControlBase::OnSetFocus](#onsetfocus)|コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナー コントロールに通知の確認はフォーカスを獲得しました。|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|独自のキーボード アクセラレータのハンドラーを提供するには、このメソッドをオーバーライドします。|  
|[CComControlBase::SendOnClose](#sendonclose)|コントロールが閉じられているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|コントロールのデータが変更をアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnRename](#sendonrename)|アドバイズ ホルダー コントロールに新しいモニカーがあることに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnSave](#sendonsave)|コントロールが保存されているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|登録されているすべてのコントロールのビューが変更されたアドバイズ シンクに通知します。|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|設定またはコントロールとの間にキーボード フォーカスを削除します。|  
|[CComControlBase::SetDirty](#setdirty)|データ メンバーを設定`m_bRequiresSave`の値に`bDirty`します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|コントロールは、その他の任意のサイズを変更できないことを示すフラグを設定します。|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|示すフラグ`IDataObjectImpl::GetData`と`CComControlBase::GetZoomInfo`からコントロールのサイズを設定する必要があります`m_sizeNatural`からではなく`m_sizeExtent`です。|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|示すフラグ`IDataObjectImpl::GetData`描画するときに HIMETRIC 単位と単位を使用する必要があります。|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|コントロールがアクティブであることを示すフラグを設定します。|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|コンテナー サポートしていることを示すフラグ、**処理**インターフェイスと OCX96 およびちらつきなしのコントロールなどの機能を制御します。|  
|[各](#m_bnegotiatedwnd)|(ちらつきのないでウィンドウ コントロールなど)、OCX96 コントロールの機能のサポートのコンテナーとコントロールがネゴシエートするかどうか、およびコントロールがウィンドウを持つかなしを示すフラグします。|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|コントロールでは、コンテナー コントロールの表示サイズが変更されたときに、形式を再構成することを示すフラグを設定します。|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|最後に保存された後、コントロールが変更を示すフラグします。|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|コントロールが本来のエクステント (スケールなし物理サイズ) のサイズを変更することを示すフラグ、コンテナーがコントロールの表示サイズを変更するとします。|  
|[CComControlBase::m_bUIActive](#m_buiactive)|メニューやツールバーなどのコントロールのユーザー インターフェイスを示すフラグはアクティブです。|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|コントロールを使用して、コンテナーが指定したウィンドウ領域を示すフラグします。|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|コントロール ウィンドウなし、されましたが、可能性がありますか今すぐウィンドウなしはありませんを示すフラグします。|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|コンテナーは、ウィンドウなしのコントロールをサポートしている場合でも、コントロールがウィンドウを持つするかを示すフラグします。|  
|[CComControlBase::m_bWndLess](#m_bwndless)|コントロールがウィンドウなしを示すフラグします。|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|コントロールに関連付けられているウィンドウ ハンドルへの参照が含まれています。|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|回数の合計数、コンテナーが (イベントを拒否しました) イベントをイベント (イベントの受け入れ) の間にある固定を解除せず停止います。|  
|[CComControlBase::m_rcPos](#m_rcpos)|コンテナーの座標で表される、コントロールの位置を (ピクセル単位)。|  
|[この](#m_sizeextent)|特定のディスプレイの HIMETRIC 単位 (各単位は 0.01 ミリメートル単位) で、コントロールの範囲。|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) コントロールの物理サイズ。|  
|[アドバイズ](#m_spadvisesink)|コンテナーのアドバイザリ コネクションへのダイレクト ポインター (コンテナーの[IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513))。|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A`CComDispatchDriver`オブジェクトを取得し、コンテナーのプロパティを設定できるように、`IDispatch`ポインター。|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|コンテナー内のコントロールのクライアントのサイトへのポインター。|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|データ オブジェクト間のアドバイザリ コネクションを保持し、アドバイズ シンクに、標準的なことを意味を提供します。|  
|[は](#m_spinplacesite)|コンテナーへのポインター[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)インターフェイス ポインター。|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|アドバイザリ コネクションを保持するための標準的な実装を提供します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)から派生した`CComControlBase`します。 ATL コントロール ウィザードを使用して標準的なコントロールや DHTML コントロールを作成するときに、ウィザードは自動的に派生クラスから`CComControlBase`します。  
  
 コントロールの作成方法の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="appearancetype"></a>CComControlBase::AppearanceType  
 場合は、オーバーライド、 **m_nAppearance**ストック プロパティは、型の**短い**します。  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>コメント  
 ATL コントロール ウィザードは、追加**m_nAppearance**ストック short 型のプロパティです。 オーバーライド`AppearanceType`別のデータ型を使用する場合。  
  
##  <a name="ccomcontrolbase"></a>CComControlBase::CComControlBase  
 コンストラクターです。  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 コントロールに関連付けられているウィンドウのハンドル。  
  
### <a name="remarks"></a>コメント  
 コントロールのサイズを 5080 × 5080 HIMETRIC 単位を初期化します ("2"X 2) を初期化し、`CComControlBase`データ メンバーの値を**NULL**または**FALSE**します。  
  
##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase  
 デストラクターです。  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>コメント  
 コントロールがウィンドウを持つ場合`~CComControlBase`を呼び出して破棄[DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682)します。  
  
##  <a name="controlqueryinterface"></a>CComControlBase::ControlQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 要求されているインターフェイスの GUID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 COM マップ テーブル内のインターフェイスを処理のみです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate  
 確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブにするか (`iVerb`と等しい`OLEIVERB_UIACTIVATE`)、ユーザー コントロールをダブルクリックしたときの動作を定義 ( `iVerb` equals `OLEIVERB_PRIMARY`)、コントロールが表示されます (`iVerb`と等しい`OLEIVERB_SHOW`)、またはコントロールをアクティブ化 (`iVerb`と等しい**OLEIVERB_INPLACEACTIVATE**)。  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値`DoVerb`です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**場合`iVerb`equals `OLEIVERB_UIACTIVATE`、 `OLEIVERB_PRIMARY`、 `OLEIVERB_SHOW`、または**OLEIVERB_INPLACEACTIVATE**、それ以外を返します**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 独自のライセンス認証の動詞を定義するには、このメソッドをオーバーライドできます。  
  
##  <a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate  
 確認、`iVerb`で使用されるパラメーター`IOleObjectImpl::DoVerb`コントロールのユーザー インターフェイスをアクティブ化してを返します**TRUE**します。  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値`DoVerb`です。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**場合`iVerb`equals `OLEIVERB_UIACTIVATE`、 `OLEIVERB_PRIMARY`、 `OLEIVERB_SHOW`、または**OLEIVERB_INPLACEACTIVATE**します。 それ以外の場合、メソッドが返す**FALSE**します。  
  
##  <a name="doverbproperties"></a>CComControlBase::DoVerbProperties  
 コントロールのプロパティ ページを表示します。  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 予約済み。  
  
 *hwndParent*  
 コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#19;](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM&#20;](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>CComControlBase::FireViewChange  
 コントロールを再描画するためのコンテナーを確認するには、このメソッドを呼び出すか、コントロールのビューが変更された登録済みアドバイズ シンクに通知します。  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 コントロールがアクティブな場合 (コントロール クラスのデータ メンバー [CComControlBase::m_bInPlaceActive](#m_binplaceactive)は**TRUE**)、コントロール全体を再描画することをコンテナーに通知します。 コントロールがアクティブでない場合は、そのコントロールの登録に通知アドバイズ シンク (コントロール クラスのデータ メンバーを[アドバイズ](#m_spadvisesink)) コントロールのビューが変更されたことです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#21;](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>CComControlBase::GetAmbientAppearance  
 取得**を示す**、現在の外観をコントロールの設定: フラット 3 d 1 の場合は 0 です。  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppearance`  
 プロパティ**を示す**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#22;](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip  
 取得**DISPID_AMBIENT_AUTOCLIP**コンテナーがコントロールの表示領域の自動クリップをサポートしているかどうかを示しますフラグ。  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutoClip*  
 プロパティ**DISPID_AMBIENT_AUTOCLIP**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientbackcolor"></a>用意されています  
 取得**DISPID_AMBIENT_BACKCOLOR**、コンテナーによって定義されたすべてのコントロールのアンビエント背景色。  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *背景色*  
 プロパティ**DISPID_AMBIENT_BACKCOLOR**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet  
 取得**DISPID_AMBIENT_CHARSET**、コンテナーによって定義されたすべてのコントロールの周囲の文字セットします。  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrCharSet*  
 プロパティ**DISPID_AMBIENT_CHARSET**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage  
 取得**ことにあります**、コンテナーによって定義されたすべてのコントロールのアンビエント コード ページ。  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>パラメーター  
 *ulCodePage*  
 プロパティ**ことにあります**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbientDisplayAsDefault  
 取得**DISPID_AMBIENT_DISPLAYASDEFAULT**、あるフラグ**TRUE**かどうか、コンテナーが既定のボタンでは、このサイトのコントロールをマーク、したがってボタン コントロールが作成されます自体が太くフレームを使用しています。  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDisplayAsDefault`  
 プロパティ**DISPID_AMBIENT_DISPLAYASDEFAULT**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName  
 取得**DISPID_AMBIENT_DISPLAYNAME**コンテナーがコントロールに指定された名前です。  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrDisplayName*  
 プロパティ**DISPID_AMBIENT_DISPLAYNAME**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientfont"></a>CComControlBase::GetAmbientFont  
 取得、コンテナーへのポインターのアンビエント`IFont`インターフェイスです。  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コンテナーへのポインターのアンビエント[IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673)インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 プロパティの場合**NULL**、ポインターが**NULL**します。 ポインターがない場合**NULL**、呼び出し元は、ポインターを解放する必要があります。  
  
##  <a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp  
 取得、コンテナーへのポインターのアンビエント**この**ディスパッチ インターフェイスです。  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コンテナーへのポインターのアンビエント[この](http://msdn.microsoft.com/library/windows/desktop/ms692695)ディスパッチ インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティの場合**NULL**、ポインターが**NULL**します。 ポインターがない場合**NULL**、呼び出し元は、ポインターを解放する必要があります。  
  
##  <a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor  
 取得**DISPID_AMBIENT_FORECOLOR**、コンテナーによって定義されたすべてのコントロールのアンビエント前景色。  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *前景色*  
 プロパティ**DISPID_AMBIENT_FORECOLOR**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID  
 取得**DISPID_AMBIENT_LOCALEID**、コンテナーによって使用される言語の識別子。  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>パラメーター  
 `lcid`  
 プロパティ**DISPID_AMBIENT_LOCALEID**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 コントロールは、この識別子を使用して、そのユーザー インターフェイスを異なる言語を調整します。  
  
##  <a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect  
 取得**DISPID_AMBIENT_MESSAGEREFLECT**コンテナーは、ウィンドウ メッセージを受信するかどうかを示すフラグ (よう`WM_DRAWITEM`) イベントとして。  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 `bMessageReflect`  
 プロパティ**DISPID_AMBIENT_MESSAGEREFLECT**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientpalette"></a>CComControlBase::GetAmbientPalette  
 取得**DISPID_AMBIENT_PALETTE**コンテナーのアクセスに使用される、`HPALETTE`です。  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `hPalette`  
 プロパティ**DISPID_AMBIENT_PALETTE**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientproperty"></a>CComControlBase::GetAmbientProperty  
 指定されたコンテナーのプロパティを取得`dispid`します。  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 取得するコンテナーのプロパティの識別子。  
  
 `var`  
 プロパティを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 ATL は、特定のプロパティを取得するヘルパー関数のセットを提供しました[用意されています](#getambientbackcolor)します。 使用可能な適切なメソッドがない場合を使用して`GetAmbientProperty`します。  
  
##  <a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft  
 取得**DISPID_AMBIENT_RIGHTTOLEFT**方向がコンテナーによってコンテンツが表示されます。  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRightToLeft*  
 プロパティ**DISPID_AMBIENT_RIGHTTOLEFT**します。 設定**TRUE**コンテンツが右から左へ表示される場合**FALSE**左右側に表示される場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits  
 取得**DISPID_AMBIENT_SCALEUNITS**コンテナーのアンビエント単位 (インチやセンチメートル) ラベルが表示されます。  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrScaleUnits*  
 プロパティ**DISPID_AMBIENT_SCALEUNITS**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles  
 取得**DISPID_AMBIENT_SHOWGRABHANDLES**コンテナーがアクティブなときにグラブ ハンドルを表示するコントロールを許可するかどうかを示すフラグ。  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowGrabHandles*  
 プロパティ**DISPID_AMBIENT_SHOWGRABHANDLES**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching  
 取得**DISPID_AMBIENT_SHOWHATCHING**コンテナーがコントロールのユーザー インターフェイスがアクティブなハッチ パターンではそれ自体を表示するコントロールを許可するかどうかを示すフラグ。  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShowHatching*  
 プロパティ**DISPID_AMBIENT_SHOWHATCHING**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics  
 取得**DISPID_AMBIENT_SUPPORTSMNEMONICS**コンテナーがニーモニックをサポートしているかどうかを示しますフラグ。  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>パラメーター  
 *bSupportsMnemonics*  
 プロパティ**DISPID_AMBIENT_SUPPORTSMNEMONICS**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign  
 取得**DISPID_AMBIENT_TEXTALIGN**コンテナーが希望するテキストの配置: 一般的な配置 (数値、テキストを左) の場合は 0、左揃えの場合は 1、中央揃えの場合は 2 および 3 は右揃えにします。  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 *nTextAlign*  
 プロパティ**DISPID_AMBIENT_TEXTALIGN**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom  
 取得**DISPID_AMBIENT_TOPTOBOTTOM**方向がコンテナーによってコンテンツが表示されます。  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>パラメーター  
 *bTopToBottom*  
 プロパティ**DISPID_AMBIENT_TOPTOBOTTOM**します。 設定**TRUE**テキストが表示されている場合上から下に向かって、 **FALSE**表示されている場合 下上からです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead  
 取得**DISPID_AMBIENT_UIDEAD**ユーザー インターフェイスの動作に対応するコントロールがあるかどうかを示しますフラグ。  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>パラメーター  
 *bUIDead*  
 プロパティ**DISPID_AMBIENT_UIDEAD**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 場合**TRUE**、コントロールが応答する必要があります。 このフラグに関係なく適用される、 **DISPID_AMBIENT_USERMODE**フラグ。 参照してください[CComControlBase::GetAmbientUserMode](#getambientusermode)します。  
  
##  <a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode  
 取得**DISPID_AMBIENT_USERMODE**、コンテナーが実行モードであるかどうかを示すフラグ ( **TRUE**) またはデザイン モード ( **FALSE**)。  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUserMode`  
 プロパティ**DISPID_AMBIENT_USERMODE**します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
##  <a name="getdirty"></a>CComControlBase::GetDirty  
 データ メンバーの値を返します`m_bRequiresSave`します。  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>戻り値  
 データ メンバーの値を返します[m_bRequiresSave](#m_brequiressave)します。  
  
### <a name="remarks"></a>コメント  
 使用してこの値を設定[CComControlBase::SetDirty](#setdirty)します。  
  
##  <a name="getzoominfo"></a>CComControlBase::GetZoomInfo  
 X と y を取得、分子と倍率の分母の値の有効なコントロールの埋め込み先編集します。  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 倍率の分子と分母を保持する構造体。 詳細については、次を参照してください。 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)します。  
  
### <a name="remarks"></a>コメント  
 ズームの倍率は、現在の大きさに対するコントロールの自然なサイズの比率です。  
  
##  <a name="inplaceactivate"></a>CComControlBase::InPlaceActivate  
 どのステート内の動詞を非アクティブ状態から移行するコントロールをさせます`iVerb`ことを示します。  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 によって実行されるアクションを示す値[IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb)します。  
  
 *prcPosRect*  
 インプレースでコントロールの位置を指すポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 アクティブ化する前に、このメソッドは、コントロールにクライアント サイトし、チェック コントロールの量が表示されており、親ウィンドウ内のコントロールの位置を取得することをチェックします。 制御を有効にすると、このメソッドは、コントロールのユーザー インターフェイスをアクティブにし、コントロールを表示するコンテナーに指示します。  
  
 このメソッドはまた、取得、 `IOleInPlaceSite`、**処理**、または**IOleInPlaceSiteWindowless**コントロールのインターフェイス ポインター コントロール クラスのデータ メンバーに格納[は](#m_spinplacesite)です。 コントロール クラスのデータ メンバー [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)、 [CComControlBase::m_bWndLess](#m_bwndless)、 [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)、および[各](#m_bnegotiatedwnd)必要に応じて、true に設定されます。  
  
##  <a name="internalgetsite"></a>CComControlBase::InternalGetSite  
 識別されたインターフェイスへのポインターのコントロールのサイトを照会するには、このメソッドを呼び出します。  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 返す必要があるインターフェイス ポインターの IID`ppUnkSite`します。  
  
 `ppUnkSite`  
 要求されたインターフェイス ポインターを受け取るポインター変数のアドレス`riid`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 サイトで要求されたインターフェイスをサポートしている場合`riid`、によって返されるポインター`ppUnkSite`します。 それ以外の場合、`ppUnkSite`は NULL に設定します。  
  
##  <a name="m_bautosize"></a>CComControlBase::m_bAutoSize  
 コントロールは、その他の任意のサイズを変更できないことを示すフラグを設定します。  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>コメント  
 このフラグはオン`IOleObjectImpl::SetExtent`し、 **TRUE**、関数が返すと、 **E_FAIL**します。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 追加する場合、**自動サイズ** オプションを選択、[ストック プロパティ](../../atl/reference/stock-properties-atl-control-wizard.md)ATL コントロール ウィザード、ウィザードのタブに自動的にコントロール クラスでこのデータ メンバーを作成、配置を作成およびプロパティ、およびサポートするための get メソッド[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)にプロパティが変更されたときに、コンテナーを自動的に通知します。  
  
##  <a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural  
 示すフラグ`IDataObjectImpl::GetData`と`CComControlBase::GetZoomInfo`からコントロールのサイズを設定する必要があります`m_sizeNatural`からではなく`m_sizeExtent`です。  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric  
 示すフラグ`IDataObjectImpl::GetData`描画するときに HIMETRIC 単位と単位を使用する必要があります。  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>コメント  
 それぞれの論理 HIMETRIC 単位は 0.01 ミリメートルです。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive  
 コントロールがアクティブであることを示すフラグを設定します。  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>コメント  
 つまり、コントロールを表示し、ウィンドウに存在する場合、表示ですがメニューおよびツールバーをアクティブなできない可能性があります。 `m_bUIActive`フラグは、メニューなどのコントロールのユーザー インターフェイスがアクティブでもを示します。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx  
 コンテナー サポートしていることを示すフラグ、**処理**インターフェイスと OCX96 およびちらつきなしのコントロールなどの機能を制御します。  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ メンバー`m_spInPlaceSite`を指す、[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)の値に応じて、インターフェイス、`m_bWndLess`と`m_bInPlaceSiteEx`フラグ。 (データ メンバー`m_bNegotiatedWnd`する必要があります**TRUE**の`m_spInPlaceSite`を有効にするポインター)。  
  
 場合`m_bWndLess`は**FALSE**と`m_bInPlaceSiteEx`は**TRUE**、`m_spInPlaceSite`は、**処理**インターフェイス ポインター。 参照してください[は、「](#m_spinplacesite)のこれらの&3; つのデータ メンバーのリレーションシップを示すします表。  
  
##  <a name="m_bnegotiatedwnd"></a>各  
 (ちらつきのないでウィンドウ コントロールなど)、OCX96 コントロールの機能のサポートのコンテナーとコントロールがネゴシエートするかどうか、およびコントロールがウィンドウを持つかなしを示すフラグします。  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 `m_bNegotiatedWnd`フラグである必要があります**TRUE**の`m_spInPlaceSite`を有効にするポインター。  
  
##  <a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize  
 コントロールでは、コンテナー コントロールの表示サイズが変更されたときに、形式を再構成することを示すフラグを設定します。  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 このフラグはオン[IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent)し、 **TRUE**、`SetExtent`の変更の表示のコンテナーに通知します。 このフラグが設定されている場合、 **OLEMISC_RECOMPOSEONRESIZE**内のビット、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)列挙体を設定することがもする必要があります。  
  
##  <a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave  
 最後に保存された後、コントロールが変更を示すフラグします。  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>コメント  
 値`m_bRequiresSave`で設定できる[CComControlBase::SetDirty](#setdirty)されで取得された[CComControlBase::GetDirty](#getdirty)します。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural  
 コントロールが本来のエクステント (スケールなし物理サイズ) のサイズを変更することを示すフラグ、コンテナーがコントロールの表示サイズを変更するとします。  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>コメント  
 このフラグはオン`IOleObjectImpl::SetExtent`し、 **TRUE**にサイズが渡された`SetExtent`に割り当てられている`m_sizeNatural`します。  
  
 渡されたサイズ`SetExtent`に常に割り当てられた`m_sizeExtent`の値に関係なく、`m_bResizeNatural`です。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_buiactive"></a>CComControlBase::m_bUIActive  
 メニューやツールバーなどのコントロールのユーザー インターフェイスを示すフラグはアクティブです。  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>コメント  
 `m_bInPlaceActive`フラグは、コントロールがアクティブな場合、それがあることを示しますがアクティブで、ユーザー インターフェイスです。  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn  
 コントロールを使用して、コンテナーが指定したウィンドウ領域を示すフラグします。  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless  
 コントロール ウィンドウなし、されましたが、可能性がありますか今すぐウィンドウなしはありませんを示すフラグします。  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly  
 コンテナーは、ウィンドウなしのコントロールをサポートしている場合でも、コントロールがウィンドウを持つするかを示すフラグします。  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_bwndless"></a>CComControlBase::m_bWndLess  
 コントロールがウィンドウなしを示すフラグします。  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ メンバー`m_spInPlaceSite`を指す、[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)の値に応じて、インターフェイス、`m_bWndLess`と[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)フラグ。 (データ メンバー[各](#m_bnegotiatedwnd)する必要があります**TRUE**の[は](#m_spinplacesite)を有効にするポインター)。  
  
 場合`m_bWndLess`は**TRUE**、`m_spInPlaceSite`は、 **IOleInPlaceSiteWindowless**インターフェイス ポインター。 参照してください[は](#m_spinplacesite)のこれらのデータ メンバーの完全な関係を示す表。  
  
##  <a name="m_hwndcd"></a>CComControlBase::m_hWndCD  
 コントロールに関連付けられているウィンドウ ハンドルへの参照が含まれています。  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents  
 回数の合計数、コンテナーが (イベントを拒否しました) イベントをイベント (イベントの受け入れ) の間にある固定を解除せず停止います。  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_rcpos"></a>CComControlBase::m_rcPos  
 コンテナーの座標で表される、コントロールの位置を (ピクセル単位)。  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_sizeextent"></a>この  
 特定のディスプレイの HIMETRIC 単位 (各単位は 0.01 ミリメートル単位) で、コントロールの範囲。  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 このサイズは、ディスプレイでスケーリングされます。 コントロールの物理サイズで指定する、`m_sizeNatural`データ メンバーし、固定されています。  
  
 グローバル関数とのピクセルにサイズを変換する[AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd)します。  
  
##  <a name="m_sizenatural"></a>CComControlBase::m_sizeNatural  
 HIMETRIC 単位 (各単位は 0.01 ミリメートル) コントロールの物理サイズ。  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 サイズの中に、このサイズは固定されて`m_sizeExtent`ディスプレイでのスケールが設定されます。  
  
 グローバル関数とのピクセルにサイズを変換する[AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd)します。  
  
##  <a name="m_spadvisesink"></a>アドバイズ  
 コンテナーのアドバイザリ コネクションへのダイレクト ポインター (コンテナーの[IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513))。  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch  
 A`CComDispatchDriver`オブジェクトを取得してから、オブジェクトのプロパティを設定できるように、`IDispatch`ポインター。  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spclientsite"></a>CComControlBase::m_spClientSite  
 コンテナー内のコントロールのクライアントのサイトへのポインター。  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
##  <a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder  
 データ オブジェクト間のアドバイザリ コネクションを保持し、アドバイズ シンクに、標準的なことを意味を提供します。  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 データ オブジェクトは、データを転送することができを実装するコントロール[IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)、そのメソッドがデータの形式と転送のメディアを指定します。  
  
 インターフェイス`m_spDataAdviseHolder`を実装する、 [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579)と[IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448)メソッドを設定し、コンテナーにアドバイザリ コネクションを削除します。 コントロールのコンテナーがサポートされているアドバイズ シンクを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)インターフェイスです。  
  
##  <a name="m_spinplacesite"></a>は  
 コンテナーへのポインター[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586)、[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461)、または[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)インターフェイス ポインター。  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 `m_spInPlaceSite`ポインターが有効な場合にのみ、 [m_bNegotiatedWnd](#m_bnegotiatedwnd)フラグは**TRUE**します。  
  
 次の表に、どのように`m_spInPlaceSite`ポインターの種類によって異なります、 [m_bWndLess](#m_bwndless)と[m_bInPlaceSiteEx](#m_binplacesiteex)データ メンバーのフラグ。  
  
|型は、「|m_bWndLess 値|m_bInPlaceSiteEx 値|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**TRUE**|**TRUE**または**FALSE**|  
|**この処理**|**FALSE**|**TRUE**|  
|`IOleInPlaceSite`|**FALSE**|**FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder  
 アドバイザリ コネクションを保持するための標準的な実装を提供します。  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このデータ メンバーをコントロール クラスを使用するには、必要がありますとして宣言するデータ メンバー コントロール クラスにします。 基本クラスの共用体で宣言されているので、コントロール クラスは、基本クラスからこのデータ メンバーを継承しません。  
  
 インターフェイス`m_spOleAdviseHolder`を実装する、 [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573)と[IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749)メソッドを設定し、コンテナーにアドバイザリ コネクションを削除します。 コントロールのコンテナーがサポートされているアドバイズ シンクを実装する必要があります、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)インターフェイスです。  
  
##  <a name="ondraw"></a>CComControlBase::OnDraw  
 コントロールを描画するには、このメソッドをオーバーライドします。  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 参照、 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)描画アスペクト比、コントロールの境界などの描画の情報を格納する構造体かに描画を最適化するかどうかとします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 既定値`OnDraw`を削除またはデバイス コンテキストを復元または何もしない設定されているフラグによって[CComControlBase::OnDrawAdvanced](#ondrawadvanced)します。  
  
 `OnDraw`メソッドは ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的にコントロール クラスに追加します。 ウィザードの既定`OnDraw`"ATL 8.0"というラベルの付いた四角形を描画します。  
  
### <a name="example"></a>例  
 例を参照してください[CComControlBase::GetAmbientAppearance](#getambientappearance)します。  
  
##  <a name="ondrawadvanced"></a>CComControlBase::OnDrawAdvanced  
 既定値`OnDrawAdvanced`描画に正規化デバイス コンテキストを準備し、コントロール クラスを呼び出し、`OnDraw`メソッドです。  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>パラメーター  
 `di`  
 参照、 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)描画アスペクト比、コントロールの境界などの描画の情報を格納する構造体かに描画を最適化するかどうかとします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 正規化せずに、コンテナーによって渡されるデバイス コンテキストをそのまま使用する場合は、このメソッドをオーバーライドします。  
  
 参照してください[CComControlBase::OnDraw](#ondraw)詳細です。  
  
##  <a name="onkillfocus"></a>CComControlBase::OnKillFocus  
 コントロール、インプレース アクティブと有効なコントロール サイトを持つそのが、コントロールがフォーカスを失ったことをコンテナーに通知を確認します。  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
##  <a name="onmouseactivate"></a>CComControlBase::OnMouseActivate  
 UI がユーザー モードにし、コントロールをアクティブ化を確認します。  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
##  <a name="onpaint"></a>CComControlBase::OnPaint  
 描画するため、コンテナーを準備し、コントロールのクライアント領域の取得、コントロール クラスの`OnDrawAdvanced`メソッドです。  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 既存の HDC します。  
  
 `lParam`  
 予約済み。  
  
 `lResult`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 常に&0; を返します。  
  
### <a name="remarks"></a>コメント  
 場合`wParam`が NULL でない`OnPaint`有効 HDC が含まれていますの代わりを使用して、前提としています[CComControlBase::m_hWndCD](#m_hwndcd)します。  
  
##  <a name="onsetfocus"></a>CComControlBase::OnSetFocus  
 コントロール、インプレース アクティブと有効なコントロール サイトを持つそのがコンテナー コントロールに通知の確認はフォーカスを獲得しました。  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMsg`  
 予約済み。  
  
 `wParam`  
 予約済み。  
  
 `lParam`  
 予約済み。  
  
 `bHandled`  
 ウィンドウ メッセージが正常に処理されたかどうかを示すフラグです。 既定値は、`FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがフォーカスを受け取ったことをコンテナーに通知を送信します。  
  
##  <a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator  
 独自のキーボード アクセラレータのハンドラーを提供するには、このメソッドをオーバーライドします。  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 予約済み。  
  
 *hRet*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 既定で返す**FALSE**します。  
  
##  <a name="sendonclose"></a>CComControlBase::SendOnClose  
 コントロールが閉じられているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがアドバイズ シンクを閉じている通知を送信します。  
  
##  <a name="sendondatachange"></a>CComControlBase::SendOnDataChange  
 コントロールのデータが変更をアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *advf*  
 指定するフラグをお勧めする方法への呼び出し[IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283)されます。 値は、 [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742)列挙します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="sendonrename"></a>CComControlBase::SendOnRename  
 アドバイズ ホルダー コントロールに新しいモニカーがあることに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>パラメーター  
 *pmk*  
 コントロールの新しいモニカーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのモニカーが変更されたことを示す通知を送信します。  
  
##  <a name="sendonsave"></a>CComControlBase::SendOnSave  
 コントロールが保存されているアドバイズ ホルダーに登録されているすべてのアドバイズ シンクに通知します。  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがデータを保存したことの通知を送信します。  
  
##  <a name="sendonviewchange"></a>CComControlBase::SendOnViewChange  
 登録されているすべてのコントロールのビューが変更されたアドバイズ シンクに通知します。  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 面またはコントロールのビューです。  
  
 *lindex*  
 ビューが変更された部分。 -1 だけは有効です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `SendOnViewChange`呼び出し[IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337)します。 唯一の値の*lindex*ビュー全体が関心のあることを示す-1 は、現在サポートされています。  
  
##  <a name="setcontrolfocus"></a>CComControlBase::SetControlFocus  
 設定またはコントロールとの間にキーボード フォーカスを削除します。  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>パラメーター  
 *bGrab*  
 場合**TRUE**を呼び出し元のコントロールにキーボード フォーカスを設定します。 場合**FALSE**フォーカスがある限り、呼び出し元のコントロールからキーボード フォーカスを削除します。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**コントロールが正常にフォーカスを得た場合それ以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウを持つコントロール、Windows API 関数の[SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312)が呼び出されます。 ウィンドウなしのコントロールの[IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745)が呼び出されます。 この呼び出しでは、ウィンドウなしのコントロールがキーボード フォーカスを取得し、ウィンドウ メッセージに応答できます。  
  
##  <a name="setdirty"></a>CComControlBase::SetDirty  
 データ メンバーを設定`m_bRequiresSave`の値に`bDirty`します。  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDirty`  
 データ メンバーの値[CComControlBase::m_bRequiresSave](#m_brequiressave)します。  
  
### <a name="remarks"></a>コメント  
 **Setdirty (true)**フラグを最後に保存されてから、コントロールが変更されたことを呼び出す必要があります。 値`m_bRequiresSave`で取得[CComControlBase::GetDirty](#getdirty)します。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

