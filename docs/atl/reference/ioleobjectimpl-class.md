---
title: "IOleObjectImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IOleObjectImpl
- ATL.IOleObjectImpl<T>
- ATL::IOleObjectImpl
- ATL::IOleObjectImpl<T>
- IOleObjectImpl
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
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
ms.openlocfilehash: b0b471b997bfdb4062f00b40864c347db78b114a
ms.lasthandoff: 02/24/2017

---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl クラス
このクラスは実装**IUnknown**コンテナーがコントロールとの通信に使用するプリンシパルのインターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IOleObjectImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|コントロールとのアドバイザリ コネクションを確立します。|  
|[IOleObjectImpl::Close](#close)|ロードを実行してから、コントロールの状態を変更します。|  
|[IOleObjectImpl::DoVerb](#doverb)|列挙されるアクションのいずれかを実行するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|コントロールを維持してきたすべて元に戻す状態を破棄するように指示します。|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|ビューからそのユーザー インターフェイスを削除するコントロールに指示します。|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|コントロールを実行し、そのウィンドウが、コントロールのユーザー インターフェイスはインストールされません。|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|別のウィンドウで開いて編集をするコントロールがされます。|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|ユーザーがコントロールをダブルクリックすると、指定したアクションを実行します。 コントロールでは、インプレース コントロールをアクティブ化するには、通常の操作を定義します。|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|新しく挿入されたコントロールをユーザーに表示します。|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|インプレース コントロールをアクティブにし、メニューやツールバーなどのコントロールのユーザー インターフェイスを示しています。|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|コントロールのアドバイザリ コネクションを列挙します。|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|コントロールのアクションを列挙します。|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|コントロールのクライアントのサイトを取得します。|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|クリップボードからデータを取得します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleObjectImpl::GetExtent](#getextent)|コントロールの表示領域の範囲を取得します。|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|コントロールの状態を取得します。|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|コントロールのモニカーを取得します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|コントロールのクラス識別子を取得します。|  
|[IOleObjectImpl::GetUserType](#getusertype)|コントロールのユーザーの種類の名前を取得します。|  
|[IOleObjectImpl::InitFromData](#initfromdata)|選択したデータからコントロールを初期化します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|コントロールの最新の状態を確認します。 ATL の実装を返します`S_OK`します。|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す状態が破棄された後です。|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|によって呼び出される[DoVerbHide](#doverbhide)後、コントロールが非表示にします。|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化した後です。|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|によって呼び出される[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで編集するためです。|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|によって呼び出される[DoVerbShow](#doverbshow)コントロールの作成後に表示します。|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|によって呼び出される[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスが起動された後です。|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す前に、状態は破棄されます。|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|によって呼び出される[DoVerbHide](#doverbhide)コントロールが非表示にします。|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化される前にします。|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|によって呼び出される[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで編集用に開く前にします。|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|によって呼び出される[DoVerbShow](#doverbshow)コントロールが表示される前にします。|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|によって呼び出される[DoVerbUIActivate](#doverbuiactivate)前に、コントロールのユーザー インターフェイスがアクティブ化されています。|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|コンテナー内のクライアントのサイトをコントロールに設定します。|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|存在する場合は、画面の配色をコントロールのアプリケーションにお勧めします。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleObjectImpl::SetExtent](#setextent)|コントロールの表示領域の範囲を設定します。|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに設定します。|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|モニカーは、コントロールに指示します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleObjectImpl::Unadvise](#unadvise)|コントロールとのアドバイザリ コネクションを削除します。|  
|[IOleObjectImpl::Update](#update)|コントロールを更新します。 ATL の実装を返します`S_OK`します。|  
  
## <a name="remarks"></a>コメント  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)インターフェイスは、コンテナーがコントロールとの通信に使用するプリンシパルのインターフェイスです。 クラス`IOleObjectImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-nameadvisea--ioleobjectimpladvise"></a><a name="advise"></a>IOleObjectImpl::Advise  
 コントロールとのアドバイザリ コネクションを確立します。  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameclosea--ioleobjectimplclose"></a><a name="close"></a>IOleObjectImpl::Close  
 ロードを実行してから、コントロールの状態を変更します。  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>コメント  
 コントロールを非アクティブにし、存在する場合は、コントロールのウィンドウを破棄します。 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave)は**TRUE**と`dwSaveOption`パラメーターは、いずれかの`OLECLOSE_SAVEIFDIRTY`または`OLECLOSE_PROMPTSAVE`閉じる前に、コントロールのプロパティを保存します。  
  
 コントロール クラスのデータ メンバーに、ポインターが保持されている[は](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite)と[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)がリリースされると、データ メンバー[各](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd)、 [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)、および[CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex)に設定されている**FALSE**します。  
  
 参照してください[IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedoverba--ioleobjectimpldoverb"></a><a name="doverb"></a>IOleObjectImpl::DoVerb  
 列挙されるアクションのいずれかを実行するコントロールに指示します。  
  
```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```  
  
### <a name="remarks"></a>コメント  
 値に応じて`iVerb`、ATL のいずれかの`DoVerb`ヘルパー関数は次のように呼び出されます。  
  
|*iVerb*値|呼び出される DoVerb ヘルパー関数|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[アンドゥ](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[埋め込み](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 参照してください[IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedoverbdiscardundoa--ioleobjectimpldoverbdiscardundo"></a><a name="doverbdiscardundo"></a>IOleObjectImpl::DoVerbDiscardUndo  
 コントロールを維持してきたすべて元に戻す状態を破棄するように指示します。  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="a-namedoverbhidea--ioleobjectimpldoverbhide"></a><a name="doverbhide"></a>IOleObjectImpl::DoVerbHide  
 非アクティブにし、コントロールのユーザー インターフェイスを削除し、コントロールを非表示にします。  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="a-namedoverbinplaceactivatea--ioleobjectimpldoverbinplaceactivate"></a><a name="doverbinplaceactivate"></a>IOleObjectImpl::DoVerbInPlaceActivate  
 コントロールを実行し、そのウィンドウが、コントロールのユーザー インターフェイスはインストールされません。  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 呼び出す場所でコントロールをアクティブに[CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)します。 しない限り、コントロール クラスのデータ メンバー`m_bWindowOnly`は**TRUE**、`DoVerbInPlaceActivate`ウィンドウなしのコントロールとしてコントロールをアクティブ化しようとするは最初に (コンテナーがサポートしている場合にのみ可能な限り[IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300))。 関数が拡張機能を持つコントロールをアクティブ化しようとした、失敗した場合 (コンテナーがサポートしている場合にのみ可能な限り[処理](http://msdn.microsoft.com/library/windows/desktop/ms693461))。 関数がない拡張機能を持つコントロールをアクティブ化しようとした、失敗した場合 (コンテナーがサポートしている場合にのみ可能な限り[ビュー](http://msdn.microsoft.com/library/windows/desktop/ms686586))。 ライセンス認証が成功した場合、関数は、コントロールがアクティブ化されて、コンテナーを通知します。  
  
##  <a name="a-namedoverbopena--ioleobjectimpldoverbopen"></a><a name="doverbopen"></a>IOleObjectImpl::DoVerbOpen  
 別のウィンドウで開いて編集をするコントロールがされます。  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
##  <a name="a-namedoverbprimarya--ioleobjectimpldoverbprimary"></a><a name="doverbprimary"></a>IOleObjectImpl::DoVerbPrimary  
 ユーザー コントロールをダブルクリックしたときの動作を定義します。  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 既定では、プロパティ ページの表示に設定します。 これがダブルクリックされたときに異なる動作を呼び出すコントロール クラスでオーバーライドすることができます。たとえば、ビデオの再生やインプレース アクティブです。  
  
##  <a name="a-namedoverbshowa--ioleobjectimpldoverbshow"></a><a name="doverbshow"></a>IOleObjectImpl::DoVerbShow  
 コントロールが表示されるようにするためのコンテナーに指示します。  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="a-namedoverbuiactivatea--ioleobjectimpldoverbuiactivate"></a><a name="doverbuiactivate"></a>IOleObjectImpl::DoVerbUIActivate  
 コントロールのユーザー インターフェイスをアクティブにし、そのメニューはコンポジット メニューに置き換えられることをコンテナーに通知します。  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcPosRec`  
 [in]四角形のコンテナーへのポインターでは、コントロールに描画する必要があります。  
  
 *hwndParent*  
 [in]コントロールを含むウィンドウのハンドル。 ATL の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="a-nameenumadvisea--ioleobjectimplenumadvise"></a><a name="enumadvise"></a>IOleObjectImpl::EnumAdvise  
 このコントロールの登録済みのアドバイザリ コネクションの列挙子を提供します。  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameenumverbsa--ioleobjectimplenumverbs"></a><a name="enumverbs"></a>IOleObjectImpl::EnumVerbs  
 このコントロールで呼び出すことによって登録されたアクション (動詞) の列挙子を提供**OleRegEnumVerbs**します。  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>コメント  
 動詞は、プロジェクトの .rgs ファイルに追加できます。 たとえば、サンプルを参照してください。RG、[円](../../visual-cpp-samples.md)サンプルです。  
  
 参照してください[IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetclientsitea--ioleobjectimplgetclientsite"></a><a name="getclientsite"></a>IOleObjectImpl::GetClientSite  
 コントロール クラスのデータ メンバーにカーソルを置きます[CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite)に*ppClientSite*し、ポインターの参照カウントをインクリメントします。  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetclipboarddataa--ioleobjectimplgetclipboarddata"></a><a name="getclipboarddata"></a>IOleObjectImpl::GetClipboardData  
 クリップボードからデータを取得します。  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetextenta--ioleobjectimplgetextent"></a><a name="getextent"></a>IOleObjectImpl::GetExtent  
 HIMETRIC 単位 (0.01 ミリメートル単位) の実行中のコントロールの表示サイズを取得します。  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>コメント  
 コントロール クラスのデータ メンバーのサイズが格納されている[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。  
  
 参照してください[IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetmiscstatusa--ioleobjectimplgetmiscstatus"></a><a name="getmiscstatus"></a>IOleObjectImpl::GetMiscStatus  
 呼び出して、コントロールの登録済みの状態に関する情報へのポインターを返します**OleRegGetMiscStatus**します。  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>コメント  
 状態情報には、コントロールとプレゼンテーションのデータでサポートされている動作が含まれています。 ステータス情報は、プロジェクトの .rgs ファイルに追加できます。  
  
 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetmonikera--ioleobjectimplgetmoniker"></a><a name="getmoniker"></a>IOleObjectImpl::GetMoniker  
 コントロールのモニカーを取得します。  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetuserclassida--ioleobjectimplgetuserclassid"></a><a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID  
 コントロールのクラス識別子を返します。  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetusertypea--ioleobjectimplgetusertype"></a><a name="getusertype"></a>IOleObjectImpl::GetUserType  
 呼び出して、コントロールのユーザー タイプ名を返す**OleRegGetUserType**します。  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>コメント  
 ユーザー タイプ名は、メニューおよびダイアログ ボックスなどのユーザー インターフェイス要素での表示に使用されます。 プロジェクトの .rgs ファイル内のユーザー型名を変更することができます。  
  
 参照してください[IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinitfromdataa--ioleobjectimplinitfromdata"></a><a name="initfromdata"></a>IOleObjectImpl::InitFromData  
 選択したデータからコントロールを初期化します。  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisuptodatea--ioleobjectimplisuptodate"></a><a name="isuptodate"></a>IOleObjectImpl::IsUpToDate  
 コントロールの最新の状態を確認します。  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[:isuptodate](http://msdn.microsoft.com/library/windows/desktop/ms686624)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonpostverbdiscardundoa--ioleobjectimplonpostverbdiscardundo"></a><a name="onpostverbdiscardundo"></a>IOleObjectImpl::OnPostVerbDiscardUndo  
 によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す状態が破棄された後です。  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻す状態が破棄された後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpostverbhidea--ioleobjectimplonpostverbhide"></a><a name="onpostverbhide"></a>IOleObjectImpl::OnPostVerbHide  
 によって呼び出される[DoVerbHide](#doverbhide)後、コントロールが非表示にします。  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが非表示にした後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpostverbinplaceactivatea--ioleobjectimplonpostverbinplaceactivate"></a><a name="onpostverbinplaceactivate"></a>IOleObjectImpl::OnPostVerbInPlaceActivate  
 によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化した後です。  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 場所に、コントロールがアクティブにされた後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpostverbopena--ioleobjectimplonpostverbopen"></a><a name="onpostverbopen"></a>IOleObjectImpl::OnPostVerbOpen  
 によって呼び出される[DoVerbOpen](#doverbopen)コントロールを開いた後に別のウィンドウで編集するためです。  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールを開いた後に別のウィンドウで編集するために実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpostverbshowa--ioleobjectimplonpostverbshow"></a><a name="onpostverbshow"></a>IOleObjectImpl::OnPostVerbShow  
 によって呼び出される[DoVerbShow](#doverbshow)コントロールの作成後に表示します。  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが表示される後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpostverbuiactivatea--ioleobjectimplonpostverbuiactivate"></a><a name="onpostverbuiactivate"></a>IOleObjectImpl::OnPostVerbUIActivate  
 によって呼び出される[DoVerbUIActivate](#doverbuiactivate)コントロールのユーザー インターフェイスが起動された後です。  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザー インターフェイスがアクティブになった後に実行するコードでこのメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbdiscardundoa--ioleobjectimplonpreverbdiscardundo"></a><a name="onpreverbdiscardundo"></a>IOleObjectImpl::OnPreVerbDiscardUndo  
 によって呼び出される[アンドゥ](#doverbdiscardundo)元に戻す前に、状態は破棄されます。  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 元に戻す状態が破棄されることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbhidea--ioleobjectimplonpreverbhide"></a><a name="onpreverbhide"></a>IOleObjectImpl::OnPreVerbHide  
 によって呼び出される[DoVerbHide](#doverbhide)コントロールが非表示にします。  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが非表示にされていることを防ぐために、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbinplaceactivatea--ioleobjectimplonpreverbinplaceactivate"></a><a name="onpreverbinplaceactivate"></a>IOleObjectImpl::OnPreVerbInPlaceActivate  
 によって呼び出される[埋め込み](#doverbinplaceactivate)インプレース コントロールがアクティブ化される前にします。  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがインプレース アクティブ化されていることを防ぐために、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbopena--ioleobjectimplonpreverbopen"></a><a name="onpreverbopen"></a>IOleObjectImpl::OnPreVerbOpen  
 によって呼び出される[DoVerbOpen](#doverbopen)コントロールを別のウィンドウで編集用に開く前にします。  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが別のウィンドウで編集するために開かれるようにするのには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbshowa--ioleobjectimplonpreverbshow"></a><a name="onpreverbshow"></a>IOleObjectImpl::OnPreVerbShow  
 によって呼び出される[DoVerbShow](#doverbshow)コントロールが表示される前にします。  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが認識されるようにするのには、エラー HRESULT を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-nameonpreverbuiactivatea--ioleobjectimplonpreverbuiactivate"></a><a name="onpreverbuiactivate"></a>IOleObjectImpl::OnPreVerbUIActivate  
 によって呼び出される[DoVerbUIActivate](#doverbuiactivate)前に、コントロールのユーザー インターフェイスがアクティブ化されています。  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザー インターフェイスがアクティブ化されていることを防ぐために、エラーの hresult 値を返すには、このメソッドをオーバーライドします。  
  
##  <a name="a-namesetclientsitea--ioleobjectimplsetclientsite"></a><a name="setclientsite"></a>IOleObjectImpl::SetClientSite  
 コンテナー内のクライアントのサイトをコントロールに設定します。  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>コメント  
 メソッドが戻ります`S_OK`します。  
  
 参照してください[IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetcolorschemea--ioleobjectimplsetcolorscheme"></a><a name="setcolorscheme"></a>IOleObjectImpl::SetColorScheme  
 存在する場合は、画面の配色をコントロールのアプリケーションにお勧めします。  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetextenta--ioleobjectimplsetextent"></a><a name="setextent"></a>IOleObjectImpl::SetExtent  
 コントロールの表示領域の範囲を設定します。  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>コメント  
 それ以外の場合、`SetExtent`が指す値を格納`psizel`コントロール クラスのデータ メンバーに[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。 この値では、HIMETRIC 単位 (0.01 ミリメートル単位) です。  
  
 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural)は**TRUE**、`SetExtent`またが指す値を格納`psizel`コントロール クラスのデータ メンバーに[CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)します。  
  
 場合は、コントロールがデータ メンバーをクラス[CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize)は**TRUE**、`SetExtent`呼び出し`SendOnDataChange`と`SendOnViewChange`アドバイズ ホルダー コントロールのサイズが変更されたことに登録されているすべてのアドバイズ シンクに通知します。  
  
 参照してください[IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesethostnamesa--ioleobjectimplsethostnames"></a><a name="sethostnames"></a>IOleObjectImpl::SetHostNames  
 アプリケーションのコンテナーおよびコンテナー ドキュメントの名前をコントロールに設定します。  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetmonikera--ioleobjectimplsetmoniker"></a><a name="setmoniker"></a>IOleObjectImpl::SetMoniker  
 モニカーは、コントロールに指示します。  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameunadvisea--ioleobjectimplunadvise"></a><a name="unadvise"></a>IOleObjectImpl::Unadvise  
 コントロールのクラスに格納されているアドバイザリ コネクションを削除`m_spOleAdviseHolder`データ メンバーです。  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameupdatea--ioleobjectimplupdate"></a><a name="update"></a>IOleObjectImpl::Update  
 コントロールを更新します。  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)

