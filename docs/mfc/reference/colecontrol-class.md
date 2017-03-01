---
title: "COleControl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControl
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, MFC
- windowless controls, MFC
- windowless controls
- controls [MFC], OLE
- controls [MFC], windowless
- COleControl class
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
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
ms.openlocfilehash: 7ef5621aaf940be3ebe2806971dfc65d06972a5a
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrol-class"></a>COleControl クラス
OLE コントロールを開発するための強力な基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleControl::COleControl](#colecontrol)|
          `COleControl` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControl::AmbientAppearance](#ambientappearance)|コントロールの現在の外観を取得します。|  
|[COleControl::AmbientBackColor](#ambientbackcolor)|アンビエント BackColor プロパティの値を返します。|  
|[COleControl::AmbientDisplayName](#ambientdisplayname)|コンテナーで指定されたコントロールの名前を返します。|  
|[COleControl::AmbientFont](#ambientfont)|アンビエント フォント プロパティの値を返します。|  
|[COleControl::AmbientForeColor](#ambientforecolor)|アンビエント前景色プロパティの値を返します。|  
|[COleControl::AmbientLocaleID](#ambientlocaleid)|コンテナーのロケール ID を返します。|  
|[COleControl::AmbientScaleUnits](#ambientscaleunits)|コンテナーで使用されるユニットの種類を返します。|  
|[COleControl::AmbientShowGrabHandles](#ambientshowgrabhandles)|グラブ ハンドルを表示するかどうかを決定します。|  
|[COleControl::AmbientShowHatching](#ambientshowhatching)|陰影を表示するかどうかを決定します。|  
|[COleControl::AmbientTextAlign](#ambienttextalign)|コンテナーで指定されたテキストの配置の種類を返します。|  
|[COleControl::AmbientUIDead](#ambientuidead)|コントロールがユーザー インターフェイスの動作に応答する必要があるかどうかを判断します。|  
|[COleControl::AmbientUserMode](#ambientusermode)|コンテナーのモードを決定します。|  
|[COleControl::BoundPropertyChanged](#boundpropertychanged)|バインドされたプロパティが変更されたことをコンテナーに通知します。|  
|[COleControl::BoundPropertyRequestEdit](#boundpropertyrequestedit)|プロパティの値を編集するアクセス許可を要求します。|  
|[COleControl::ClientToParent](#clienttoparent)|コンテナーの原点に対するポイントには、コントロールの原点に変換します。|  
|[COleControl::ClipCaretRect](#clipcaretrect)|コントロールが重なっている場合は、カレット長方形を調整します。|  
|[COleControl::ControlInfoChanged](#controlinfochanged)|コントロールによって処理されるニーモニックのセットが変更された後は、この関数を呼び出します。|  
|[COleControl::DisplayError](#displayerror)|コントロールのユーザーへのストックのエラー イベントを表示します。|  
|[COleControl::DoClick](#doclick)|ストックの実装`DoClick`メソッドです。|  
|[使って](#dopropexchange)|プロパティをシリアル化、`COleControl`オブジェクトです。|  
|[COleControl::DoSuperclassPaint](#dosuperclasspaint)|Windows コントロールからサブクラス化されている OLE コントロールを再描画します。|  
|[COleControl::EnableSimpleFrame](#enablesimpleframe)|コントロールのシンプルなフレームのサポートを有効にします。|  
|[COleControl::ExchangeExtent](#exchangeextent)|コントロールの幅と高さをシリアル化します。|  
|[COleControl::ExchangeStockProps](#exchangestockprops)|コントロールのストック プロパティをシリアル化します。|  
|[COleControl::ExchangeVersion](#exchangeversion)|コントロールのバージョン番号をシリアル化します。|  
|[COleControl::FireClick](#fireclick)|素材を発生させる`Click`イベントです。|  
|[COleControl::FireDblClick](#firedblclick)|素材を発生させる`DblClick`イベントです。|  
|[COleControl::FireError](#fireerror)|素材を発生させる`Error`イベントです。|  
|[COleControl::FireEvent](#fireevent)|カスタム イベントを発生させます。|  
|[COleControl::FireKeyDown](#firekeydown)|素材を発生させる`KeyDown`イベントです。|  
|[COleControl::FireKeyPress](#firekeypress)|素材を発生させる`KeyPress`イベントです。|  
|[COleControl::FireKeyUp](#firekeyup)|素材を発生させる`KeyUp`イベントです。|  
|[COleControl::FireMouseDown](#firemousedown)|素材を発生させる`MouseDown`イベントです。|  
|[COleControl::FireMouseMove](#firemousemove)|素材を発生させる`MouseMove`イベントです。|  
|[COleControl::FireMouseUp](#firemouseup)|素材を発生させる`MouseUp`イベントです。|  
|[COleControl::FireReadyStateChange](#firereadystatechange)|コントロールの準備状態が変化したときにイベントを発生させます。|  
|[アクティブ](#getactivationpolicy)|サポートするコントロールの既定のアクティブ化の動作を変更して、`IPointerInactive`インターフェイスです。|  
|[COleControl::GetAmbientProperty](#getambientproperty)|指定されたアンビエント プロパティの値を返します。|  
|[COleControl::GetAppearance](#getappearance)|ストックの外観プロパティの値を返します。|  
|[COleControl::GetBackColor](#getbackcolor)|ストック BackColor プロパティの値を返します。|  
|[COleControl::GetBorderStyle](#getborderstyle)|ストック BorderStyle プロパティの値を返します。|  
|[COleControl::GetCapture](#getcapture)|アクティブなウィンドウなしコントロール オブジェクトにマウスのキャプチャがあるかどうかを決定します。|  
|[COleControl::GetClassID](#getclassid)|コントロールの OLE クラス ID を取得します。|  
|[COleControl::GetClientOffset](#getclientoffset)|コントロールの四角形領域の左上隅と、クライアント領域の左上隅の差を取得します。|  
|[COleControl::GetClientRect](#getclientrect)|コントロールのクライアント領域のサイズを取得します。|  
|[COleControl::GetClientSite](#getclientsite)|コンテナー内の現在のクライアント サイトへのポインターのオブジェクトを照会します。|  
|[オン](#getcontrolflags)|制御フラグの設定を取得します。|  
|[COleControl::GetControlSize](#getcontrolsize)|OLE コントロールのサイズと位置を返します。|  
|[COleControl::GetDC](#getdc)|ウィンドウなしのコントロールをコンテナーからデバイス コンテキストを取得するための手段を提供します。|  
|[COleControl::GetEnabled](#getenabled)|ストックの Enabled プロパティの値を返します。|  
|[COleControl::GetExtendedControl](#getextendedcontrol)|コンテナーに属する拡張コントロール オブジェクトへのポインターを取得します。|  
|[COleControl::GetFocus](#getfocus)|コントロールにフォーカスがあるかどうかを決定します。|  
|[COleControl::GetFont](#getfont)|ストック フォント プロパティの値を返します。|  
|[COleControl::GetFontTextMetrics](#getfonttextmetrics)|メトリックを返します、`CFontHolder`オブジェクトです。|  
|[COleControl::GetForeColor](#getforecolor)|ストックの前景色プロパティの値を返します。|  
|[COleControl::GetHwnd](#gethwnd)|ストック hWnd プロパティの値を返します。|  
|[COleControl::GetMessageString](#getmessagestring)|メニュー項目のステータス バーのテキストを提供します。|  
|[COleControl::GetNotSupported](#getnotsupported)|ユーザーがコントロールのプロパティの値にアクセスできなくなります。|  
|[COleControl::GetReadyState](#getreadystate)|コントロールの準備状態を返します。|  
|[COleControl::GetRectInContainer](#getrectincontainer)|コンテナーを基準として、コントロールの四角形を返します。|  
|[COleControl::GetStockTextMetrics](#getstocktextmetrics)|ストック フォント プロパティのメトリックを返します。|  
|[COleControl::GetText](#gettext)|テキストまたはキャプションのストック プロパティの値を返します。|  
|[COleControl::GetWindowlessDropTarget](#getwindowlessdroptarget)|ウィンドウなしのコントロールを対象のドラッグ アンド ドロップ操作を許可するようにオーバーライドします。|  
|[COleControl::InitializeIIDs](#initializeiids)|コントロールを使用して、Iid の基本クラスを通知します。|  
|[COleControl::InternalGetFont](#internalgetfont)|返します。、`CFontHolder`ストック フォント プロパティのオブジェクト。|  
|[COleControl::InternalGetText](#internalgettext)|ストックのキャプションまたはテキストのプロパティを取得します。|  
|[中](#internalsetreadystate)|コントロールの準備状態を設定し、準備完了状態変更イベントが発生します。|  
|[COleControl::InvalidateControl](#invalidatecontrol)|それを再描画を発生させる、表示されているコントロールの領域を無効にします。|  
|[COleControl::InvalidateRgn](#invalidatergn)|指定された領域内のコンテナー ウィンドウのクライアント領域を無効にします。 ウィンドウなしのコントロールが再描画領域で使用できます。|  
|[COleControl::IsConvertingVBX](#isconvertingvbx)|OLE コントロールの専用の読み込みを許可します。|  
|[COleControl::IsModified](#ismodified)|コントロールの状態が変更されたかどうかを判断します。|  
|[COleControl::IsOptimizedDraw](#isoptimizeddraw)|コンテナーが現在の描画操作の最適化された描画をサポートするかどうかを示します。|  
|[COleControl::IsSubclassedControl](#issubclassedcontrol)|Windows コントロールをサブクラス化が制御を決定する呼び出されます。|  
|[COleControl::Load](#load)|以前の非同期データをリセットし、新しいコントロールの非同期プロパティの読み込みを開始します。|  
|[COleControl::LockInPlaceActive](#lockinplaceactive)|コンテナーによって、コントロールを非アクティブ化できるかどうかを判断します。|  
|[COleControl::OnAmbientPropertyChange](#onambientpropertychange)|アンビエント プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnAppearanceChanged](#onappearancechanged)|ストックの外観プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnBackColorChanged](#onbackcolorchanged)|ストック BackColor プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnBorderStyleChanged](#onborderstylechanged)|ストックの BorderStyle プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnClick](#onclick)|ストック Click を発生させると呼ばれるイベントです。|  
|[COleControl::OnClose](#onclose)|コントロールに通知する`IOleControl::Close`が呼び出されています。|  
|[COleControl::OnDoVerb](#ondoverb)|コントロールの動詞が実行された後に呼び出されます。|  
|[オーバライド](#ondraw)|自動的に再描画するコントロールが要求されたときに呼び出されます。|  
|[COleControl::OnDrawMetafile](#ondrawmetafile)|メタファイル デバイス コンテキストを使用して自動的に再描画するコントロールが要求されたときに、コンテナーによって呼び出されます。|  
|[COleControl::OnEdit](#onedit)|OLE コントロールの UI がアクティブ化するコンテナーによって呼び出されます。|  
|[COleControl::OnEnabledChanged](#onenabledchanged)|ストックの Enabled プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnEnumVerbs](#onenumverbs)|コントロールの動詞を列挙するコンテナーによって呼び出されます。|  
|[COleControl::OnEventAdvise](#oneventadvise)|イベント ハンドラーが接続またはコントロールから切断されたときに呼び出されます。|  
|[COleControl::OnFontChanged](#onfontchanged)|ストック フォント プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnForeColorChanged](#onforecolorchanged)|ストックの前景色プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnFreezeEvents](#onfreezeevents)|コントロールのイベントが固定されているか、マスクされていないときに呼び出されます。|  
|[COleControl::OnGetColorSet](#ongetcolorset)|コントロールに通知する`IOleObject::GetColorSet`が呼び出されています。|  
|[COleControl::OnGetControlInfo](#ongetcontrolinfo)|コンテナーにニーモニック情報を提供します。|  
|[COleControl::OnGetDisplayString](#ongetdisplaystring)|プロパティ値を表す文字列を取得するには、呼び出されます。|  
|[COleControl::OnGetInPlaceMenu](#ongetinplacemenu)|コンテナーのメニューにマージするコントロールのメニューのハンドルを要求します。|  
|[COleControl::OnGetNaturalExtent](#ongetnaturalextent)|提案されたサイズと拡張モードに最も近いコントロールの表示のサイズを取得するためにオーバーライドします。|  
|[COleControl::OnGetPredefinedStrings](#ongetpredefinedstrings)|プロパティの使用可能な値を表す文字列を返します。|  
|[COleControl::OnGetPredefinedValue](#ongetpredefinedvalue)|定義済みの文字列に対応する値を返します。|  
|[COleControl::OnGetViewExtent](#ongetviewextent)|(2 パスの描画を有効にするを使用できます)、コントロールの表示領域のサイズを取得するためにオーバーライドします。|  
|[COleControl::OnGetViewRect](#ongetviewrect)|コントロールのサイズを特定の位置以降にある四角形に変換するためにオーバーライドします。|  
|[COleControl::OnGetViewStatus](#ongetviewstatus)|コントロールのビュー状態を取得するためにオーバーライドします。|  
|[COleControl::OnHideToolBars](#onhidetoolbars)|コントロールが非アクティブ化された UI である場合に、コンテナーによって呼び出されます。|  
|[COleControl::OnInactiveMouseMove](#oninactivemousemove)|マウス ポインターのディスパッチの下にある非アクティブなコントロールのコンテナーを持つようオーバーライド`WM_MOUSEMOVE`メッセージをコントロールします。|  
|[COleControl::OnInactiveSetCursor](#oninactivesetcursor)|マウス ポインターのディスパッチの下にある非アクティブなコントロールのコンテナーを持つようオーバーライド`WM_SETCURSOR`メッセージをコントロールします。|  
|[COleControl::OnKeyDownEvent](#onkeydownevent)|ストックの KeyDown イベントが発生した後に呼び出されます。|  
|[COleControl::OnKeyPressEvent](#onkeypressevent)|ストックの KeyPress イベントが発生した後に呼び出されます。|  
|[COleControl::OnKeyUpEvent](#onkeyupevent)|ストックの KeyUp イベントが発生した後に呼び出されます。|  
|[COleControl::OnMapPropertyToPage](#onmappropertytopage)|プロパティの編集に使用するプロパティ ページを示します。|  
|[COleControl::OnMnemonic](#onmnemonic)|コントロールのニーモニック キーが押されたときに呼び出されます。|  
|[COleControl::OnProperties](#onproperties)|コントロールの「プロパティ」動詞を呼び出したときに呼び出されます。|  
|[COleControl::OnQueryHitPoint](#onqueryhitpoint)|コントロールの表示には、指定された点が重複して かどうかは、クエリにオーバーライドします。|  
|[COleControl::OnQueryHitRect](#onqueryhitrect)|コントロールの表示には、任意の場所で指定された四角形が重複して かどうかは、クエリにオーバーライドします。|  
|[COleControl::OnRenderData](#onrenderdata)|指定した形式でデータを取得するためにフレームワークによって呼び出されます。|  
|[COleControl::OnRenderFileData](#onrenderfiledata)|指定した形式でファイルからデータを取得するためにフレームワークによって呼び出されます。|  
|[COleControl::OnRenderGlobalData](#onrenderglobaldata)|指定した形式でのグローバル メモリからデータを取得するためにフレームワークによって呼び出されます。|  
|[COleControl::OnResetState](#onresetstate)|コントロールのプロパティを既定値にリセットします。|  
|[COleControl::OnSetClientSite](#onsetclientsite)|コントロールに通知する`IOleControl::SetClientSite`が呼び出されています。|  
|[COleControl::OnSetData](#onsetdata)|コントロールのデータを別の値に置き換えます。|  
|[COleControl::OnSetExtent](#onsetextent)|コントロールの大きさが変更された後に呼び出されます。|  
|[COleControl::OnSetObjectRects](#onsetobjectrects)|コントロールのサイズが変更された後に呼び出されます。|  
|[COleControl::OnShowToolBars](#onshowtoolbars)|コントロールの UI がアクティブになったときに呼び出されます。|  
|[COleControl::OnTextChanged](#ontextchanged)|在庫テキストまたは文字列のキャプション プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnWindowlessMessage](#onwindowlessmessage)|ウィンドウなしのコントロールを (マウスとキーボードのメッセージ) 以外のウィンドウ メッセージを処理します。|  
|[COleControl::ParentToClient](#parenttoclient)|コントロールの原点に対するポイントには、コンテナーの原点に変換します。|  
|[COleControl::PostModalDialog](#postmodaldialog)|モーダル ダイアログ ボックスが閉じられたことをコンテナーに通知します。|  
|[COleControl::PreModalDialog](#premodaldialog)|モーダル ダイアログ ボックスが表示されるコンテナーに通知します。|  
|[COleControl::RecreateControlWindow](#recreatecontrolwindow)|破棄し、コントロールのウィンドウを再作成します。|  
|[COleControl::Refresh](#refresh)|強制的にコントロールの外観の再描画をします。|  
|[COleControl::ReleaseCapture](#releasecapture)|マウスのキャプチャを解放します。|  
|[COleControl::ReleaseDC](#releasedc)|ウィンドウなしのコントロールのコンテナーのディスプレイ デバイス コンテキストを解放します。|  
|[COleControl::ReparentControlWindow](#reparentcontrolwindow)|コントロールのウィンドウの親をリセットします。|  
|[COleControl::ResetStockProps](#resetstockprops)|初期化`COleControl`ストック プロパティが既定値にします。|  
|[COleControl::ResetVersion](#resetversion)|所定の値にバージョン番号を初期化します。|  
|[COleControl::ScrollWindow](#scrollwindow)|ウィンドウなしのコントロールを表示、インプレース アクティブ イメージ内の領域をスクロールを使用します。|  
|[COleControl::SelectFontObject](#selectfontobject)|デバイス コンテキストにカスタム フォントのプロパティを選択します。|  
|[それ](#selectstockfont)|デバイス コンテキストには、ストック フォント プロパティを選択します。|  
|[COleControl::SerializeExtent](#serializeextent)|シリアル化またはコントロールの表示領域を初期化します。|  
|[COleControl::SerializeStockProps](#serializestockprops)|シリアル化または初期化、 `COleControl` ストック プロパティです。|  
|[COleControl::SerializeVersion](#serializeversion)|シリアル化またはコントロールのバージョン情報を初期化します。|  
|[COleControl::SetAppearance](#setappearance)|ストックの外観プロパティの値を設定します。|  
|[COleControl::SetBackColor](#setbackcolor)|ストック BackColor プロパティの値を設定します。|  
|[COleControl::SetBorderStyle](#setborderstyle)|ストックの BorderStyle プロパティの値を設定します。|  
|[COleControl::SetCapture](#setcapture)|コントロールの代わりにマウスのキャプチャを所有している、実行するコントロールのコンテナーのウィンドウが発生します。|  
|[COleControl::SetControlSize](#setcontrolsize)|OLE コントロールのサイズと位置を設定します。|  
|[COleControl::SetEnabled](#setenabled)|ストックの Enabled プロパティの値を設定します。|  
|[COleControl::SetFocus](#setfocus)|コントロールの代わりに入力フォーカスを所有している、実行するコントロールのコンテナーのウィンドウが発生します。|  
|[COleControl::SetFont](#setfont)|ストック フォント プロパティの値を設定します。|  
|[COleControl::SetForeColor](#setforecolor)|ストックの前景色プロパティの値を設定します。|  
|[COleControl::SetInitialSize](#setinitialsize)|OLE コントロールのコンテナーに初めて表示したときのサイズを設定します。|  
|[COleControl::SetModifiedFlag](#setmodifiedflag)|コントロールの変更済みの状態を変更します。|  
|[COleControl::SetNotPermitted](#setnotpermitted)|編集要求が失敗したことを示します。|  
|[COleControl::SetNotSupported](#setnotsupported)|ユーザーがコントロールのプロパティの値を変更できないようにします。|  
|[COleControl::SetRectInContainer](#setrectincontainer)|コンテナーを基準として、コントロールの四角形を設定します。|  
|[COleControl::SetText](#settext)|テキストまたはキャプションのストック プロパティの値を設定します。|  
|[COleControl::ThrowError](#throwerror)|OLE コントロールでエラーが発生したことを通知します。|  
|[COleControl::TransformCoords](#transformcoords)|変換では、コンテナーとコントロール間の値を調整します。|  
|[COleControl::TranslateColor](#translatecolor)|変換、 **OLE_COLOR**値を**COLORREF**値。|  
|[COleControl::WillAmbientsBeValidDuringLoad](#willambientsbevalidduringload)|かどうかアンビエントできるプロパティは次に、コントロールが読み込まれるときを決定します。|  
|[COleControl::WindowProc](#windowproc)|ウィンドウ プロシージャを提供する`COleControl`オブジェクトです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControl::DrawContent](#drawcontent)|コントロールの外観を更新する必要がある場合に、フレームワークによって呼び出されます。|  
|[COleControl::DrawMetafile](#drawmetafile)|メタファイルのデバイス コンテキストを使用している場合に、フレームワークによって呼び出されます。|  
|[COleControl::IsInvokeAllowed](#isinvokeallowed)|オートメーション メソッドの呼び出しを有効にします。|  
|[COleControl::SetInitialDataFormats](#setinitialdataformats)|コントロールによってサポートされるデータ形式のリストを初期化するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 派生した`CWnd`、このクラスは、Windows のウィンドウ オブジェクトのすべての機能、およびイベントの発生やメソッドとプロパティをサポートする機能など、ole に固有の追加機能を継承します。  
  
 OLE コントロールは、OLE コンテナー アプリケーションに挿入することができ、イベントの発生し、公開するメソッドとプロパティ、コンテナーの双方向のシステムを使用して、コンテナーと通信します。 標準の OLE コンテナーのみサポートされている OLE コントロールの基本的な機能に注意してください。 OLE コントロールの拡張機能をサポートすることはありません。 イベントの発生は、コントロールで実行されている特定のアクションの結果として、コンテナーにイベントが送信されるときに発生します。 さらに、コンテナーは、公開されたメンバー関数に似たメソッドやプロパティのセットと C++ クラスのデータ メンバーを使用して、コントロールと通信します。 これにより、開発者は、コントロールの外観を制御し、特定のアクションが発生するときに、コンテナーを通知することができます。  
  
## <a name="windowless-controls"></a>ウィンドウなしのコントロール  
 OLE コントロールはウィンドウなしの使用の場でアクティブにできます。 ウィンドウなしのコントロールには、重要な利点があります。  
  
-   ウィンドウなしのコントロールは、透過的で四角形以外を指定できます。  
  
-   オブジェクトのインスタンスのサイズと作成時刻を縮小します。  
  
 コントロールでは、ウィンドウは必要ありません。 ウィンドウが提供するサービスは、1 つの共有ウィンドウ (通常はコンテナーの) と多少のディスパッチ コードを使用して簡単に提供できます。 ウィンドウは、ほとんどの場合、オブジェクトで不必要に複雑です。  
  
 ウィンドウなしのアクティベーションを使用する場合は、コンテナー (これには、ウィンドウが必要) をコントロールのウィンドウが用意されてそれ以外の場合はサービスを提供する担当します。 たとえば、コントロールは、キーボード フォーカスを照会、マウスのキャプチャのクエリ、またはデバイス コンテキストを取得する必要がある、これらの操作は、コンテナーによって管理されます。 `COleControl`[操作ウィンドウなしのメンバー関数](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df)コンテナーでこれらの操作を呼び出します。  
  
 コンテナーのデリゲートがコントロールのメッセージを入力ウィンドウなしのアクティベーションを有効にすると、`IOleInPlaceObjectWindowless`インターフェイス (の拡張機能[IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)ウィンドウなしのサポート用)。 `COleControl`このインターフェイスの実装は、マウスの調整を適切に調整した後、コントロールのメッセージ マップからこれらのメッセージはディスパッチされます。 メッセージ マップに対応するエントリを追加することで、通常のウィンドウ メッセージのようにこれらのメッセージを処理できます。  
  
 ウィンドウなしのコントロールでは、常に使用することは、 `COleControl` 、対応するのではなくのメンバー関数`CWnd`メンバー関数またはその関連する Windows API 関数です。  
  
 OLE コントロール オブジェクトは、ウィンドウをアクティブになったが、使用頻度の低いアクティブな移行のために必要な作業量が上がるし、遷移の速度がダウンした場合にのみ作成もできます。 これは問題としない: たとえば、テキスト ボックスのグリッドを検討してください。 ときに列全体を上下カーソル、各コントロールがあります、インプレース アクティブ化され、非アクティブ化します。 アクティブ/アクティブでない変換の速度は、スクロール速度に直接影響します。  
  
 OLE コントロール フレームワークの開発の詳細については、記事を参照してください。 [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)と[の概要: MFC ActiveX コントロール プログラムを作成する](../../mfc/reference/mfc-activex-control-wizard.md)です。 OLE コントロール、およびちらつきなしのコントロールなどの最適化に関する情報を参照してください。 [MFC ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="a-nameambientbackcolora--colecontrolambientbackcolor"></a><a name="ambientbackcolor"></a>COleControl::AmbientBackColor  
 アンビエント BackColor プロパティの値を返します。  
  
```  
OLE_COLOR AmbientBackColor();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのアンビエント BackColor プロパティ、存在する場合の現在の値。 プロパティがサポートされていない場合、この関数は、システム定義されている Windows の背景色を返します。  
  
### <a name="remarks"></a>コメント  
 アンビエント BackColor プロパティは、すべてのコントロールにすることはあり、コンテナーによって定義されます。 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientdisplaynamea--colecontrolambientdisplayname"></a><a name="ambientdisplayname"></a>COleControl::AmbientDisplayName  
 コンテナーがコントロールに割り当てられている名前は、ユーザーに表示されるエラー メッセージで使用できます。  
  
```  
CString AmbientDisplayName();
```  
  
### <a name="return-value"></a>戻り値  
 OLE コントロールの名前。 既定では長さ&0; の文字列です。  
  
### <a name="remarks"></a>コメント  
 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientfonta--colecontrolambientfont"></a><a name="ambientfont"></a>COleControl::AmbientFont  
 アンビエント フォント プロパティの値を返します。  
  
```  
LPFONTDISP AmbientFont();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのアンビエント フォント ディスパッチ インターフェイスへのポインター。 既定値は**NULL**します。 戻り値と等しくない場合**NULL**、呼び出すことによって、フォントを解放する必要がその[:release](http://msdn.microsoft.com/library/windows/desktop/ms682317)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 アンビエントのフォント プロパティは、コンテナーによって定義されたすべてのコントロールで使用できます。コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientforecolora--colecontrolambientforecolor"></a><a name="ambientforecolor"></a>COleControl::AmbientForeColor  
 アンビエント前景色プロパティの値を返します。  
  
```  
OLE_COLOR AmbientForeColor();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのアンビエント前景色プロパティ、存在する場合の現在の値。 サポートされていない場合、この関数は、Windows システムで定義されているテキストの色を返します。  
  
### <a name="remarks"></a>コメント  
 アンビエント前景色プロパティは、すべてのコントロールにすることはあり、コンテナーによって定義されます。 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientlocaleida--colecontrolambientlocaleid"></a><a name="ambientlocaleid"></a>COleControl::AmbientLocaleID  
 コンテナーのロケール ID を返します。  
  
```  
LCID AmbientLocaleID();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのロケール Id のプロパティが存在する場合の値。 このプロパティがサポートされていない場合、この関数は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールは、ロケール Id を使用して、特定のロケールのユーザー インターフェイスを調整します。 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientappearancea--colecontrolambientappearance"></a><a name="ambientappearance"></a>COleControl::AmbientAppearance  
 コントロール オブジェクトの現在の外観の設定を取得します。  
  
```  
short AmbientAppearance();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの外観。  
  
- **0**外観をフラット  
  
- **1** 3D 表示  
  
### <a name="remarks"></a>コメント  
 現在の値を取得するには、この関数を呼び出して、**を示す**コントロールのプロパティです。  
  
##  <a name="a-nameambientscaleunitsa--colecontrolambientscaleunits"></a><a name="ambientscaleunits"></a>COleControl::AmbientScaleUnits  
 コンテナーで使用されるユニットの種類を返します。  
  
```  
CString AmbientScaleUnits();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのアンビエント ScaleUnits を含む文字列。 このプロパティがサポートされていない場合、この関数は長さ&0; の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 位置または twip やセンチメートルなどの選択された単位ラベルが付いたディメンションを表示するコンテナーのアンビエント ScaleUnits プロパティを使用できます。 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientshowgrabhandlesa--colecontrolambientshowgrabhandles"></a><a name="ambientshowgrabhandles"></a>COleControl::AmbientShowGrabHandles  
 コンテナーがアクティブなときにグラブ ハンドルを表示するコントロールをできるかどうかを決定します。  
  
```  
BOOL AmbientShowGrabHandles();
```  
  
### <a name="return-value"></a>戻り値  
 グラブ ハンドルを表示する場合は 0 以外。それ以外の場合 0 を返します。 このプロパティがサポートされていない場合はこの関数は&0; 以外を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientshowhatchinga--colecontrolambientshowhatching"></a><a name="ambientshowhatching"></a>COleControl::AmbientShowHatching  
 コンテナーがのハッチ自体を表示するコントロールを許可するかどうかを決定場合に、パターン UI がアクティブなです。  
  
```  
BOOL AmbientShowHatching();
```  
  
### <a name="return-value"></a>戻り値  
 ハッチ パターンが表示される場合は 0 以外。それ以外の場合 0 を返します。 このプロパティがサポートされていない場合はこの関数は&0; 以外を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambienttextaligna--colecontrolambienttextalign"></a><a name="ambienttextalign"></a>COleControl::AmbientTextAlign  
 コントロールのコンテナーが希望するアンビエント テキストの配置を決定します。  
  
```  
short AmbientTextAlign();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーのアンビエント プロパティの状態。 このプロパティがサポートされていない場合、この関数は 0 を返します。  
  
 有効な戻り値の一覧を次に示します。  
  
|戻り値|説明|  
|------------------|-------------|  
|0|一般的な配置 (数値、テキストを左に) です。|  
|1|左揃え|  
|2|Center |  
|3|右揃え|  
  
### <a name="remarks"></a>コメント  
 このプロパティは、すべての組み込みコントロールで使用できるコンテナーによって定義されます。 コンテナーが、このプロパティをサポートする必要がないことに注意してください。  
  
##  <a name="a-nameambientuideada--colecontrolambientuidead"></a><a name="ambientuidead"></a>COleControl::AmbientUIDead  
 コンテナーがユーザー インターフェイスの動作に対応するコントロールを希望するかどうかを判断します。  
  
```  
BOOL AmbientUIDead();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、コントロールがユーザー インターフェイスの動作に応答する必要があります。それ以外の場合 0 を返します。 このプロパティがサポートされていない場合、この関数は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、コンテナーが設定**TRUE**デザイン モードでします。  
  
##  <a name="a-nameambientusermodea--colecontrolambientusermode"></a><a name="ambientusermode"></a>COleControl::AmbientUserMode  
 コンテナーがデザイン モードまたはユーザー モードであるかどうかを判断します。  
  
```  
BOOL AmbientUserMode();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーがユーザー モードである場合は 0 以外(デザイン モード) ではそれ以外の場合 0 を返します。 このプロパティがサポートされていない場合、この関数は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 たとえば、コンテナーが設定**FALSE**デザイン モードでします。  
  
##  <a name="a-nameboundpropertychangeda--colecontrolboundpropertychanged"></a><a name="boundpropertychanged"></a>COleControl::BoundPropertyChanged  
 バインドされたプロパティ値が変更されたことを通知します。  
  
```  
void BoundPropertyChanged(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのバインド プロパティのディスパッチの ID。  
  
### <a name="remarks"></a>コメント  
 これは、変更をしないプロパティを通じて行われた場合でも、プロパティの変更の値は、メソッドを設定するたびに呼び出す必要があります。 メンバー変数にマップされているバインドされたプロパティの特に注意してください。 このようなメンバー、変数の変更をいつ`BoundPropertyChanged`呼び出す必要があります。  
  
##  <a name="a-nameboundpropertyrequestedita--colecontrolboundpropertyrequestedit"></a><a name="boundpropertyrequestedit"></a>COleControl::BoundPropertyRequestEdit  
 アクセス許可を要求、`IPropertyNotifySink`コントロールによって提供されるバインドされたプロパティ値を変更するインターフェイスです。  
  
```  
BOOL BoundPropertyRequestEdit(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのバインド プロパティのディスパッチの ID。  
  
### <a name="return-value"></a>戻り値  
 変更は許可されている場合は 0 以外それ以外の場合 0 を返します。 既定値は&0; 以外の値です。  
  
### <a name="remarks"></a>コメント  
 アクセス許可が拒否された場合は、コントロールには、プロパティ変更の価値をこと必要がありますはできません。 これについては、無視またはプロパティの値を変更しようとするアクションが失敗していること。  
  
##  <a name="a-nameclienttoparenta--colecontrolclienttoparent"></a><a name="clienttoparent"></a>COleControl::ClientToParent  
 座標に変換`pPoint`親座標にします。  
  
```  
virtual void ClientToParent(
    LPCRECT lprcBounds, 
    LPPOINT pPoint) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lprcBounds`  
 コンテナー内の OLE コントロールの境界へのポインター。 クライアント領域ではなく、境界線とスクロール バーを含むコントロール全体の領域。  
  
 `pPoint`  
 親 (コンテナー) の座標に変換するには、OLE クライアント領域ポイントへのポインター。  
  
### <a name="remarks"></a>コメント  
 入力時に`pPoint`(コントロールのクライアント領域の左上隅) の OLE コントロールのクライアント領域の原点に対する相対パスです。 出力に`pPoint`親 (コンテナーの左上隅) の原点に対する相対パスです。  
  
##  <a name="a-nameclipcaretrecta--colecontrolclipcaretrect"></a><a name="clipcaretrect"></a>COleControl::ClipCaretRect  
 これには完全または部分的に適用して、不透明なオブジェクトによって場合は、カレット長方形を調整します。  
  
```  
BOOL ClipCaretRect(LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 入力時にへのポインター、 [RECT](../../mfc/reference/rect-structure1.md)に合わせて調整するカレット領域を格納する構造体。 出力では、調整されたカレット領域または**NULL**カレット長方形が完全に覆わ場合。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 カレットは、点滅する線、ブロック、または通常テキストやグラフィックを挿入する位置を示すビットマップです。  
  
 ウィンドウなしのオブジェクトがなしキャレットを安全に表示できないかどうかのキャレットが部分的または完全に覆われているオブジェクト。 そのため、するために、オブジェクトで使用できる`ClipCaretRect`カレットを調整する (縮小) クリッピング領域に適合するようにします。  
  
 カレットを作成するオブジェクトがカレットの四角形に送信する`ClipCaretRect`カレットの調整済みの四角形を使用します。 かどうかキャレットはまったく表示されず、このメソッドは**FALSE**キャレットが表示されないすべての例ではこのとします。  
  
##  <a name="a-namecolecontrola--colecontrolcolecontrol"></a><a name="colecontrol"></a>COleControl::COleControl  
 `COleControl` オブジェクトを構築します。  
  
```  
COleControl();
```  
  
### <a name="remarks"></a>コメント  
 この関数が直接呼び出される通常はありません。 代わりに OLE コントロールは通常、そのクラス ファクトリが作成されます。  
  
##  <a name="a-namecontrolinfochangeda--colecontrolcontrolinfochanged"></a><a name="controlinfochanged"></a>COleControl::ControlInfoChanged  
 ニーモニックと、コントロールでサポートされているセットが変更されたときに、この関数を呼び出します。  
  
```  
void ControlInfoChanged();
```  
  
### <a name="remarks"></a>コメント  
 この通知を受け取るとコントロールのコンテナーは呼び出しを行うことによってニーモニックと、新しいセットを取得[IOleControl::GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730)します。 コンテナーがこの通知に応答する必要がないことに注意してください。  
  
##  <a name="a-namedisplayerrora--colecontroldisplayerror"></a><a name="displayerror"></a>COleControl::DisplayError  
 (イベント ハンドラーは、エラーの表示を抑制しました) しない限り、株価のエラー イベントが処理された後に、フレームワークによって呼び出されます。  
  
```  
virtual void DisplayError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    LPCTSTR lpszSource,  
    LPCTSTR lpszHelpFile,  
    UINT nHelpID);
```  
  
### <a name="parameters"></a>パラメーター  
 *scode*  
 報告するステータス コードの値。 有効なコードの一覧については、記事を参照してください。 [ActiveX コントロール: 高度なトピック](../../mfc/mfc-activex-controls-advanced-topics.md)します。  
  
 `lpszDescription`  
 レポートされるエラーの説明です。  
  
 *lpszSource*  
 エラー (通常は、OLE コントロール モジュールの名前) を生成するモジュールの名前。  
  
 `lpszHelpFile`  
 エラーの説明を含むヘルプ ファイルの名前。  
  
 `nHelpID`  
 レポートされるエラーのヘルプ コンテキスト ID。  
  
### <a name="remarks"></a>コメント  
 既定の動作に含まれているエラーの説明を含むメッセージ ボックスを表示する`lpszDescription`です。  
  
 エラーの表示方法をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="a-namedoclicka--colecontroldoclick"></a><a name="doclick"></a>COleControl::DoClick  
 マウスをシミュレートするコントロールの動作 をクリックします。  
  
```  
void DoClick();
```  
  
### <a name="remarks"></a>コメント  
 オーバーライド可能な`COleControl::OnClick`メンバー関数が呼び出され、在庫コントロールによってサポートされている場合、イベントが発生されます をクリックします。  
  
 この関数はサポート、 `COleControl` DoClick と呼ばれる、ストック メソッドの基本クラスです。 詳細については、記事を参照してください。 [ActiveX コントロール: メソッド](../../mfc/mfc-activex-controls-methods.md)します。  
  
##  <a name="a-namedopropexchangea--colecontroldopropexchange"></a><a name="dopropexchange"></a>使って  
 読み込みまたはストリーム、またはプロパティのセットなどの永続的なストレージ表現からコントロールを格納するときに、フレームワークによって呼び出されます。  
  
```  
virtual void DoPropExchange(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、`CPropExchange`オブジェクトです。 フレームワークでは、方向など、プロパティ交換のコンテキストを確立するには、このオブジェクトを提供します。  
  
### <a name="remarks"></a>コメント  
 この関数での呼び出しは通常、 **px _**ファミリの読み込みまたは OLE コントロールの特定のユーザー定義プロパティを格納する関数。  
  
 この関数のオーバーライドされたバージョンがでサポートされるストック プロパティをシリアル化制御ウィザードは OLE コントロール プロジェクトの作成に使用する場合`COleControl`基底クラスの関数を呼び出して`COleControl::DoPropExchange`します。 OLE コントロールにユーザー定義のプロパティを追加すると、新しいプロパティをシリアル化するには、この関数を変更する必要があります。 シリアル化の詳細については、記事を参照してください。 [ActiveX コントロール: シリアル化する](../../mfc/mfc-activex-controls-serializing.md)です。  
  
##  <a name="a-namedosuperclasspainta--colecontroldosuperclasspaint"></a><a name="dosuperclasspaint"></a>COleControl::DoSuperclassPaint  
 Windows コントロールからサブクラス化されている OLE コントロールを再描画します。  
  
```  
void DoSuperclassPaint(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コントロールのコンテナーのデバイス コンテキストへのポインター。  
  
 `rcBounds`  
 コントロールが描画される領域です。  
  
### <a name="remarks"></a>コメント  
 この関数では、アクティブでない OLE コントロールの描画を適切に処理します。 この関数は OLE コントロール Windows のコントロールをサブクラス化とで呼び出す必要がある場合にのみ使用、`OnDraw`コントロールの機能です。  
  
 この関数は、Windows コントロールをサブクラス化の詳細については、記事を参照してください。 [ActiveX コントロール: Windows コントロールをサブクラス化](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)します。  
  
##  <a name="a-namedrawcontenta--colecontroldrawcontent"></a><a name="drawcontent"></a>COleControl::DrawContent  
 コントロールの外観を更新する必要がある場合に、フレームワークによって呼び出されます。  
  
```  
void DrawContent(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。  
  
 `rc`  
 四角形の領域に描画されます。  
  
### <a name="remarks"></a>コメント  
 この関数は、オーバーライド可能な`OnDraw`関数です。  
  
##  <a name="a-namedrawmetafilea--colecontroldrawmetafile"></a><a name="drawmetafile"></a>COleControl::DrawMetafile  
 メタファイルのデバイス コンテキストを使用している場合に、フレームワークによって呼び出されます。  
  
```  
void DrawMetafile(
    CDC* pDC,  
    CRect& rc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 メタファイルのデバイス コンテキストへのポインター。  
  
 `rc`  
 四角形の領域に描画されます。  
  
##  <a name="a-nameenablesimpleframea--colecontrolenablesimpleframe"></a><a name="enablesimpleframe"></a>COleControl::EnableSimpleFrame  
 OLE コントロールのシンプルなフレームの特性を有効にします。  
  
```  
void EnableSimpleFrame();
```  
  
### <a name="remarks"></a>コメント  
 このような特性は、他のコントロールのビジュアル コンテインメントですが真ではなく OLE 包含をサポートするためにコントロールをできるようにします。 例をいくつかのコントロールの内部でのグループ ボックスとなります。 これらのコントロールが含まれている場合、OLE ではありませんが、同じグループ ボックスです。  
  
##  <a name="a-nameexchangeextenta--colecontrolexchangeextent"></a><a name="exchangeextent"></a>COleControl::ExchangeExtent  
 シリアル化またはコントロールの範囲の状態を初期化します (そのディメンションに**HIMETRIC**単位)。  
  
```  
BOOL ExchangeExtent(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトです。 フレームワークでは、方向など、プロパティ交換のコンテキストを確立するには、このオブジェクトを提供します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は通常の既定の実装によって呼び出される`COleControl::DoPropExchange`です。  
  
##  <a name="a-nameexchangestockpropsa--colecontrolexchangestockprops"></a><a name="exchangestockprops"></a>COleControl::ExchangeStockProps  
 シリアル化またはコントロールのストック プロパティの状態を初期化します。  
  
```  
void ExchangeStockProps(CPropExchange* pPX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)オブジェクトです。 フレームワークでは、方向など、プロパティ交換のコンテキストを確立するには、このオブジェクトを提供します。  
  
### <a name="remarks"></a>コメント  
 この関数は通常の既定の実装によって呼び出される`COleControl::DoPropExchange`です。  
  
##  <a name="a-nameexchangeversiona--colecontrolexchangeversion"></a><a name="exchangeversion"></a>COleControl::ExchangeVersion  
 シリアル化またはコントロールのバージョン情報の状態を初期化します。  
  
```  
BOOL ExchangeVersion(
    CPropExchange* pPX,  
    DWORD dwVersionDefault,  
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPX`  
 ポインター、`CPropExchange`オブジェクトです。 フレームワークでは、方向など、プロパティ交換のコンテキストを確立するには、このオブジェクトを提供します。  
  
 `dwVersionDefault`  
 コントロールの現在のバージョン番号。  
  
 `bConvert`  
 永続的なデータを保存、または既に読み込まれているのと同じ形式で保持するときは、最新の形式に変換するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功したは 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 通常、これがある最初の関数のコントロールのオーバーライドによって呼び出されます`COleControl::DoPropExchange`します。 この関数は永続的なデータのバージョン番号を読み取るし、version 属性の設定を読み込むときに、 [CPropExchange](../../mfc/reference/cpropexchange-class.md)それに応じてオブジェクトです。 保存する場合、この関数は、永続的なデータのバージョン番号を書き込みます。  
  
 永続化とバージョン管理の詳細については、記事を参照してください。 [ActiveX コントロール: シリアル化する](../../mfc/mfc-activex-controls-serializing.md)です。  
  
##  <a name="a-namefireclicka--colecontrolfireclick"></a><a name="fireclick"></a>COleControl::FireClick  
 アクティブなコントロールの上にマウスがクリックされたときに、フレームワークによって呼び出されます。  
  
```  
void FireClick();
```  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 クリック イベントが発生する自動発生させるには、コントロールのイベント マップが必要ストック Click イベントが定義されています。  
  
##  <a name="a-namefiredblclicka--colecontrolfiredblclick"></a><a name="firedblclick"></a>COleControl::FireDblClick  
 アクティブなコントロール上にマウスがダブルクリックされたときに、フレームワークによって呼び出されます。  
  
```  
void FireDblClick();
```  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 DblClick イベントが発生する自動発生させるには、コントロールのイベント マップ ストックの DblClick イベントが定義されている必要があります。  
  
##  <a name="a-namefireerrora--colecontrolfireerror"></a><a name="fireerror"></a>COleControl::FireError  
 ストックのエラー イベントを発生させます。  
  
```  
void FireError(
    SCODE scode,  
    LPCTSTR lpszDescription,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *scode*  
 報告するステータス コードの値。 有効なコードの一覧については、記事を参照してください。 [ActiveX コントロール: 高度なトピック](../../mfc/mfc-activex-controls-advanced-topics.md)します。  
  
 `lpszDescription`  
 レポートされるエラーの説明です。  
  
 `nHelpID`  
 レポートされるエラーのヘルプの ID。  
  
### <a name="remarks"></a>コメント  
 このイベントは、コントロール内でエラーが発生したことをコードでは、適切な位置で通知する方法を提供します。 クリックするか、MouseMove などの他のストック イベントとは異なり、フレームワークによってエラーが発生しません。  
  
 プロパティの get 関数、プロパティ セット関数、またはオートメーション メソッド中に発生するエラーを報告するためには、呼び出す[COleControl::ThrowError](#throwerror)します。  
  
 OLE コントロールの株式のエラー イベントは、使用の実装、`SCODE`値。 コントロールは、このイベントを使用していて、Visual Basic 4.0 で使用するためのものでは場合は、エラーが発生する、 `SCODE` Visual Basic では、値はサポートされていません。  
  
 これを解決するには、手動で変更、`SCODE`コントロールのパラメーターです。ODL ファイルを**長い**します。 さらに、任意のカスタム イベント、メソッド、またはプロパティを使用する、`SCODE`パラメーターにも同じ問題が発生します。  
  
##  <a name="a-namefireeventa--colecontrolfireevent"></a><a name="fireevent"></a>COleControl::FireEvent  
 省略可能な引数の数に、コントロールからユーザー定義のイベントを発生させます。  
  
```  
void AFX_CDECL FireEvent(
    DISPID dispid,  
    BYTE* pbParams,  
 ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 発生するイベントのディスパッチの ID。  
  
 `pbParams`  
 イベントのパラメーターの型の記述子です。  
  
### <a name="remarks"></a>コメント  
 通常この関数は呼び出せません直接します。 代わりには、コントロールのクラス宣言のイベント マップのセクションで、イベント発生関数を呼び出します。  
  
 `pbParams`引数がスペースで区切られた一連の**vts _**します。 スペース (コンマではない) で区切られるこれらの値の&1; つ以上は、関数のパラメーター リストを指定します。 次の値を指定できます。  
  
|シンボル|パラメーターの型|  
|------------|--------------------|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_FONT**|**この\***|  
|**VTS_HANDLE**|`HWND`|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
  
> [!NOTE]
>  追加のバリアント定数は、例外として、すべてのバリアント型に対して定義されている**VTS_FONT**と**VTS_PICTURE**、variant データ定数へのポインターを提供します。 使用してこれらの定数がという名前の**付け**`constantname`規則です。 たとえば、 **VTS_PCOLOR**へのポインター、 **VTS_COLOR**定数です。  
  
##  <a name="a-namefirekeydowna--colecontrolfirekeydown"></a><a name="firekeydown"></a>COleControl::FireKeyDown  
 コントロールの UI のアクティブなときにキーが押されたときに、フレームワークによって呼び出されます。  
  
```  
void FireKeyDown(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnChar`  
 押されたキーの仮想キー コード値へのポインター。 標準的な仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 KeyDown イベントが発生する自動発生させるには、コントロールのイベント マップ ストックの KeyDown イベントが定義されている必要があります。  
  
##  <a name="a-namefirekeypressa--colecontrolfirekeypress"></a><a name="firekeypress"></a>COleControl::FireKeyPress  
 キーが押され、コンテナー内でカスタム コントロールの UI のアクティブなときにリリースされたときに、フレームワークによって呼び出されます。  
  
```  
void FireKeyPress(USHORT* pnChar);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnChar`  
 押されたキーの文字の値へのポインター。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 イベントの受信者を変更する`pnChar`、たとえば、すべて小文字を大文字に変換します。 変更された文字を確認する場合は、オーバーライド`OnKeyPressEvent`します。  
  
 KeyPress イベントが発生する自動発生させるには、コントロールのイベント マップ ストック KeyPress イベントが定義されている必要があります。  
  
##  <a name="a-namefirekeyupa--colecontrolfirekeyup"></a><a name="firekeyup"></a>COleControl::FireKeyUp  
 コンテナー内でカスタム コントロールが UI のアクティブな状態でキーを離したときに、フレームワークによって呼び出されます。  
  
```  
void FireKeyUp(
    USHORT* pnChar,  
    short nShiftState);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnChar`  
 リリースのキーの仮想キー コード値へのポインター。 標準的な仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 KeyUp イベントが発生する自動発生させるには、コントロールのイベント マップ ストックの KeyUp イベントが定義されている必要があります。  
  
##  <a name="a-namefiremousedowna--colecontrolfiremousedown"></a><a name="firemousedown"></a>COleControl::FireMouseDown  
 アクティブなカスタム コントロール上でマウス ボタンが押されたときに、フレームワークによって呼び出されます。  
  
```  
void FireMouseDown(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>パラメーター  
 `nButton`  
 押されたマウス ボタンの数値。 これは、次の値のいずれかを含めることができます。  
  
- **LEFT_BUTTON**マウスの左ボタンが押されています。  
  
- **MIDDLE_BUTTON**マウスの中央ボタンが押されています。  
  
- **RIGHT_BUTTON**マウスの右ボタンが押されています。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
 *x*  
 マウス ボタンが押されたとき、カーソルの x 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
 *y*  
 マウス ボタンが押されたとき、カーソルの y 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 MouseDown イベントが発生する自動発生させるには、コントロールのイベント マップを行うには、ストック MouseDown イベントが定義されている必要があります。  
  
##  <a name="a-namefiremousemovea--colecontrolfiremousemove"></a><a name="firemousemove"></a>COleControl::FireMouseMove  
 アクティブなカスタム コントロール上でカーソルが移動したときに、フレームワークによって呼び出されます。  
  
```  
void FireMouseMove(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>パラメーター  
 `nButton`  
 押されたマウス ボタンの数値。 次の値の組み合わせが含まれています。  
  
- **LEFT_BUTTON**アクション中にマウスの左ボタンが押さでした。  
  
- **MIDDLE_BUTTON**アクション中にマウスの中央ボタンが押さでした。  
  
- **RIGHT_BUTTON**アクション中にマウスの右ボタンが押さでした。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
 *x*  
 カーソルの x 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
 *y*  
 カーソルの y 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 MouseMove イベントが発生する自動発生させるには、コントロールのイベント マップ ストック MouseMove イベントが定義されている必要があります。  
  
##  <a name="a-namefiremouseupa--colecontrolfiremouseup"></a><a name="firemouseup"></a>COleControl::FireMouseUp  
 アクティブなカスタム コントロール上でマウス ボタンが離されたときに、フレームワークによって呼び出されます。  
  
```  
void FireMouseUp(
    short nButton,  
    short nShiftState,  
    OLE_XPOS_PIXELS x,  
    OLE_YPOS_PIXELS y);
```  
  
### <a name="parameters"></a>パラメーター  
 `nButton`  
 離されたマウス ボタンの数値。 次の値のいずれかを取ります。  
  
- **LEFT_BUTTON**マウスの左ボタンが離されました。  
  
- **MIDDLE_BUTTON**マウスの中央ボタンが離されました。  
  
- **RIGHT_BUTTON**右マウス ボタンが離されました。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
 *x*  
 マウス ボタンが離されたときのカーソルの x 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
 *y*  
 マウス ボタンが離されたときのカーソルの y 座標。 座標では、コントロール ウィンドウの左上隅に対して相対的です。  
  
### <a name="remarks"></a>コメント  
 このイベントがカスタムのイベントとして定義されている場合は、イベントが発生したときに決定します。  
  
 MouseUp イベントが発生する自動発生させるには、コントロールのイベント マップ ストックの MouseUp イベントが定義されている必要があります。  
  
##  <a name="a-namefirereadystatechangea--colecontrolfirereadystatechange"></a><a name="firereadystatechange"></a>COleControl::FireReadyStateChange  
 コントロールの準備完了状態の現在の値を持つイベントを発生させます。  
  
```  
void FireReadyStateChange();
```  
  
### <a name="remarks"></a>コメント  
 準備完了の状態は、次の値のいずれかになります。  
  
 **READYSTATE_UNINITIALIZED**  
 既定の初期化状態  
  
 **READYSTATE_LOADING**  
 コントロールには、そのプロパティが現在読み込んでください。  
  
 **READYSTATE_LOADED**  
 コントロールが初期化されています。  
  
 **READYSTATE_INTERACTIVE**  
 コントロールが対話型にするのには、十分なデータが非同期データがまだ読み込まれています。  
  
 `READYSTATE_COMPLETE`  
 コントロールにそのすべてのデータがあります。  
  
 使用[GetReadyState](#getreadystate)コントロールの現在の対応状況を判断します。  
  
 [InternalSetReadyState](#internalsetreadystate)準備完了の状態を指定すると、値に変更し、呼び出す`FireReadyStateChange`します。  
  
##  <a name="a-namegetactivationpolicya--colecontrolgetactivationpolicy"></a><a name="getactivationpolicy"></a>アクティブ  
 サポートするコントロールの既定のアクティブ化の動作を変更して、`IPointerInactive`インターフェイスです。  
  
```  
virtual DWORD GetActivationPolicy();
```  
  
### <a name="return-value"></a>戻り値  
 フラグの組み合わせ、 **POINTERINACTIVE**列挙します。 使用できるフラグは次のとおりです。  
  
 **POINTERINACTIVE_ACTIVATEONENTRY**  
 オブジェクトはインプレースでマウスがマウスの移動操作中に入ったときにアクティブ化をする必要があります。  
  
 **POINTERINACTIVE_DEACTIVATEONLEAVE**  
 オブジェクトは、マウスの移動操作中に、オブジェクトからマウスが離れるときに、非アクティブにする必要があります。  
  
 **POINTERINACTIVE_ACTIVATEONDRAG**  
 オブジェクトはインプレース ドラッグ中に上にマウスをドラッグするとアクティブ化する必要があり、操作をドロップします。  
  
### <a name="remarks"></a>コメント  
 ときに、`IPointerInactive`インターフェイスが有効にすると、コンテナーは、`WM_SETCURSOR`と`WM_MOUSEMOVE`メッセージです。 `COleControl`このインターフェイスの実装は、マウスの調整を適切に調整した後、コントロールのメッセージ マップからこれらのメッセージはディスパッチされます。  
  
 コンテナーを受信するたびに、`WM_SETCURSOR`または`WM_MOUSEMOVE`マウス ポインターをサポートする非アクティブなオブジェクトを含むメッセージ`IPointerInactive`を呼び出す必要が`GetActivationPolicy`からの戻り値のフラグ、インターフェイス、 **POINTERINACTIVE**列挙します。  
  
 メッセージ マップに対応するエントリを追加することで、通常のウィンドウ メッセージと同じようにこれらのメッセージを処理できます。 ハンドラーでは、使用しないように、`m_hWnd`メンバー変数 (またはそれを使用する任意のメンバー関数) 最初にその値があること以外**NULL**します。  
  
 任意のオブジェクトのための複数のマウス カーソルを設定やマウス移動イベントを発生させるは、このような特別な視覚的フィードバックを出すだけで返す必要があります、 **POINTERINACTIVE_ACTIVATEONENTRY**フラグを設定し、アクティブな場合にのみ、フィードバックを描画します。 コンテナーが埋め込み先ですぐにアクティブ化してへの呼び出しをトリガーした同じメッセージを転送、オブジェクトには、このフラグが返された場合`GetActivationPolicy`します。  
  
 どちらの場合、 **POINTERINACTIVE_ACTIVATEONENTRY**と**POINTERINACTIVE_DEACTIVATEONLEAVE**フラグが返された場合、オブジェクトはオブジェクトの上にマウスがのみアクティブ化します。 専用の場合、 **POINTERINACTIVE_ACTIVATEONENTRY**フラグが返されると、オブジェクトはマウスが最初にオブジェクトをしたときに一度のみアクティブ化します。  
  
 対象の OLE のドラッグ アンド ドロップ操作の非アクティブなコントロールをすることもできます。 これは、ドロップ先としてコントロールのウィンドウを登録できるようにするために、上にオブジェクトがドラッグ時点でコントロールをアクティブ化する必要があります。 ドラッグ中に発生する可能性のライセンス認証を返す、 **POINTERINACTIVE_ACTIVATEONDRAG**フラグ。  
  
 [!code-cpp[NVC_MFCAxCtl&#1;](../../mfc/reference/codesnippet/cpp/colecontrol-class_1.cpp)]  
  
 情報がやり取りされる`GetActivationPolicy`コンテナーによってキャッシュされないようにする必要があります。 代わりに、マウスはアクティブでないオブジェクトを入力するたびに、このメソッドを呼び出す必要があります。  
  
 コンテナーをそれ以降にディスパッチ インプレース、マウスが移動したときにアクティブ化する非アクティブなオブジェクトを要求しない場合`WM_SETCURSOR`メッセージをこのオブジェクトを呼び出して[OnInactiveSetCursor](#oninactivesetcursor)オブジェクトの上にマウス ポインターがまだ限りです。  
  
 有効にすると、`IPointerInactive`通常インターフェイスでは常にマウス メッセージの処理に対応しているコントロールをすることを意味します。 サポートしていないコンテナーでこの動作を取得する、`IPointerInactive`インターフェイスをコントロールが表示される場合、常にアクティブにしておく必要がありますので、コントロール、**されて**そのフラグ。 ただし、このフラグを防ぐためをコンテナーに有効になってはサポート`IPointerInactive`を指定することも、 **OLEMISC_IGNOREACTIVATEWHENVISIBLE**フラグ。  
  
 [!code-cpp[NVC_MFCAxCtl&#10;](../../mfc/reference/codesnippet/cpp/colecontrol-class_2.cpp)]  
  
##  <a name="a-namegetambientpropertya--colecontrolgetambientproperty"></a><a name="getambientproperty"></a>COleControl::GetAmbientProperty  
 コンテナーのアンビエント プロパティの値を取得します。  
  
```  
BOOL GetAmbientProperty(
    DISPID dispid,  
    VARTYPE vtProp,  
    void* pvProp);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispid*  
 目的のアンビエント プロパティのディスパッチの ID。  
  
 `vtProp`  
 返される値の型を指定するバリアント型タグ`pvProp`します。  
  
 `pvProp`  
 戻り値またはプロパティの値を受け取る変数のアドレスへのポインター。 This ポインターの実際の型で指定された型が一致する必要があります`vtProp`します。  
  
|vtProp|PvProp の種類|  
|------------|--------------------|  
|`VT_BOOL`|**BOOL\***|  
|`VT_BSTR`|**CString\***|  
|`VT_I2`|**短い\***|  
|`VT_I4`|**長い\***|  
|`VT_R4`|**浮動小数点数\***|  
|`VT_R8`|**二重\***|  
|`VT_CY`|**CY\***|  
|**VT_COLOR**|**OLE_COLOR\***|  
|**VT_DISPATCH**|**LPDISPATCH\***|  
|**VT_FONT**|**LPFONTDISP\***|  
  
### <a name="return-value"></a>戻り値  
 アンビエント プロパティがサポートされている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用する場合`GetAmbientProperty`アンビエント DisplayName プロパティと ScaleUnits プロパティを取得するには、次のように設定します。`vtProp`に`VT_BSTR`と`pvProp`に**CString\***します。 アンビエント フォント プロパティを取得する場合は、設定`vtProp`に**VT_FONT**と`pvProp`に**LPFONTDISP\***します。  
  
 ある関数が既に提供されて共通のアンビエント プロパティのように注意してください[AmbientBackColor](#ambientbackcolor)と[AmbientFont](#ambientfont)します。  
  
##  <a name="a-namegetappearancea--colecontrolgetappearance"></a><a name="getappearance"></a>COleControl::GetAppearance  
 コントロールの外観のストック プロパティの Get 機能を実装します。  
  
```  
short GetAppearance ();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値として現在の外観の設定を指定する、**短い**( `VT_I2`) 成功した場合の値します。 コントロールの外観が 3D の場合、コントロールの外観がフラットと 1 の場合、この値は 0 です。  
  
##  <a name="a-namegetbackcolora--colecontrolgetbackcolor"></a><a name="getbackcolor"></a>COleControl::GetBackColor  
 コントロールのストック BackColor プロパティの Get 機能を実装します。  
  
```  
OLE_COLOR GetBackColor();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値として現在の背景色を指定する、 **OLE_COLOR**正常終了した場合の値します。 この値に変換できる、 **COLORREF**への呼び出しで値`TranslateColor`です。  
  
##  <a name="a-namegetborderstylea--colecontrolgetborderstyle"></a><a name="getborderstyle"></a>COleControl::GetBorderStyle  
 コントロールのストック BorderStyle プロパティの Get 機能を実装します。  
  
```  
short GetBorderStyle();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールに通常の境界線がある場合は 1コントロールに境界があるない場合は 0。  
  
##  <a name="a-namegetcapturea--colecontrolgetcapture"></a><a name="getcapture"></a>COleControl::GetCapture  
 指定するかどうか、`COleControl`オブジェクトには、マウスのキャプチャ。  
  
```  
CWnd* GetCapture();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールがアクティブでウィンドウの場合は、返す**この**コントロールがマウスのキャプチャ (ようにコントロールのコンテナーによって決定されます) を持っている場合または**NULL**キャプチャがあるない場合。  
  
 それ以外の場合、取得、`CWnd`をマウスのキャプチャを持つオブジェクト (と同じ`CWnd::GetCapture`)。  
  
### <a name="remarks"></a>コメント  
 アクティブなウィンドウなしのコントロールがマウスを受け取るときにキャプチャ[SetCapture](#setcapture)が呼び出されます。  
  
##  <a name="a-namegetclassida--colecontrolgetclassid"></a><a name="getclassid"></a>COleControl::GetClassID  
 コントロールの OLE クラス ID を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual HRESULT GetClassID(LPCLSID pclsid) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pclsid の値*  
 クラス ID の場所へのポインター  
  
### <a name="return-value"></a>戻り値  
 呼び出しが正常に終了した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、実装によって、 [IMPLEMENT_OLECREATE_EX](class-factories-and-licensing.md#implement_olecreate_ex)します。  
  
##  <a name="a-namegetclientoffseta--colecontrolgetclientoffset"></a><a name="getclientoffset"></a>COleControl::GetClientOffset  
 コントロールの四角形領域の左上隅と、クライアント領域の左上隅の差を取得します。  
  
```  
virtual void GetClientOffset(long* pdxOffset, long* pdyOffset) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pdxOffset*  
 OLE コントロールのクライアント領域の横方向のオフセットへのポインター。  
  
 *pdyOffset*  
 OLE コントロールのクライアント領域の垂直方向のオフセットへのポインター。  
  
### <a name="remarks"></a>コメント  
 OLE コントロールには、コンテナー内の四角形の領域があります。 コントロールのクライアント領域は、境界線とスクロール バーを除くコントロール領域です。 オフセットを取得して`GetClientOffset`コントロールの四角形領域の左上隅と、クライアント領域の左上隅の違いです。 コントロールの標準的な境界線とスクロール バー以外のクライアントではない要素の場合は、オフセットを指定するには、この関数をオーバーライドします。  
  
##  <a name="a-namegetclientrecta--colecontrolgetclientrect"></a><a name="getclientrect"></a>COleControl::GetClientRect  
 コントロールのクライアント領域のサイズを取得します。  
  
```  
virtual void GetClientRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 ポインター、`RECT`ウィンドウなしのコントロールのクライアント領域の大きさを含む構造体です。 つまり、ウィンドウの縁、フレーム、スクロール バー、およびなどのコントロールのサイズ。 `lpRect`パラメーターは、コントロールのクライアントの四角形の位置のサイズを示します。  
  
##  <a name="a-namegetclientsitea--colecontrolgetclientsite"></a><a name="getclientsite"></a>COleControl::GetClientSite  
 コンテナー内の現在のクライアント サイトへのポインターのオブジェクトを照会します。  
  
```  
LPOLECLIENTSITE GetClientSite();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーで、コントロールの現在のクライアント サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 インスタンスに返されたポインターが指す`IOleClientSite`します。 `IOleClientSite` 、コンテナーによって実装されるインターフェイスは、そのコンテキストのオブジェクトのビュー: その記憶域、ユーザー インターフェイス、およびその他のリソースを取得して、ドキュメントに固定されています。  
  
##  <a name="a-namegetcontrolflagsa--colecontrolgetcontrolflags"></a><a name="getcontrolflags"></a>オン  
 制御フラグの設定を取得します。  
  
```  
virtual DWORD GetControlFlags();
```  
  
### <a name="return-value"></a>戻り値  
 ControlFlags 列挙体にフラグの論理和の組み合わせです。  
  
 `enum ControlFlags {`  
  
 `fastBeginPaint = 0x0001,`  
  
 `clipPaintDC = 0x0002,`  
  
 `pointerInactive = 0x0004,`  
  
 `noFlickerActivate = 0x0008,`  
  
 `windowlessActivate = 0x0010,`  
  
 `canOptimizeDraw = 0x0020,`  
  
 `};`  
  
### <a name="remarks"></a>コメント  
 既定では、`GetControlFlags`返します`fastBeginPaint | clipPaintDC`します。  
  
 `fastBeginPaint`  
 かどうかは、begin ペイントを使用して関数に合わせた OLE コントロールの代わりに、 [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) API (既定で設定)。  
  
 `clipPaintDC`  
 設定しない場合への呼び出しを無効に`IntersectClipRect`による`COleControl`処理速度の利点は、結果を取得します。 ウィンドウなしのアクティベーションを使用している場合、フラグの効果はありません。  
  
 `pointerInactive`  
 場合は、有効にすると、コントロールがアクティブな間は、マウスとの対話を提供`COleControl`の実装、`IPointerInactive`インターフェイスで、既定で無効にします。  
  
 `noFlickerActivate`  
 場合、余分な描画操作とそれに伴うちらつきがなくなります。 描画を行うコントロールと同様、非アクティブとアクティブな状態のときに使用します。 ウィンドウなしのアクティベーションを使用している場合、フラグの効果はありません。  
  
 `windowlessActivate`  
 場合は、コントロールがウィンドウなしのアクティベーションを使用することを示します。  
  
 `canOptimizeDraw`  
 場合は、コンテナーがサポートされている場合、コントロールが最適化された描画を実行することを示します。  
  
 詳細については`GetControlFlags`OLE コントロールの他の最適化を参照してくださいと[ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
##  <a name="a-namegetcontrolsizea--colecontrolgetcontrolsize"></a><a name="getcontrolsize"></a>COleControl::GetControlSize  
 OLE コントロール ウィンドウのサイズを取得します。  
  
```  
void GetControlSize(
    int* pcx,  
    int* pcy);
```  
  
### <a name="parameters"></a>パラメーター  
 *pcx*  
 コントロールの幅をピクセル単位で指定します。  
  
 *pcy*  
 コントロールの高さをピクセル単位で指定します。  
  
### <a name="remarks"></a>コメント  
 Windows のコントロールのすべての座標がコントロールの左上隅に対して相対的に、注意してください。  
  
##  <a name="a-namegetdca--colecontrolgetdc"></a><a name="getdc"></a>COleControl::GetDC  
 コンテナーからウィンドウなしのオブジェクトの get 画面 (または互換性のある) デバイス コンテキストを提供します。  
  
```  
CDC* GetDC(
    LPCRECT lprcRect = NULL,
    DWORD dwFlags = OLEDC_PAINTBKGND);
```  
  
### <a name="parameters"></a>パラメーター  
 *lprcRect*  
 四角形のウィンドウなしのコントロールへのポインターがコントロールのクライアント座標で再描画しようとするとします。 **NULL**完全なオブジェクトの範囲のことを意味します。  
  
 `dwFlags`  
 デバイス コンテキストの属性を描画します。 選択肢があります。  
  
- **OLEDC_NODRAW**オブジェクトがだけでは、ディスプレイ デバイスに関する情報を取得する描画をすべてを実行するデバイス コンテキストを使用しないことを示します。 コンテナーにさらに処理することがなく、ウィンドウの DC に渡します必要があります。  
  
- **OLEDC_PAINTBKGND**コンテナーがドメイン コント ローラーを返す前に背景を描画することを要求します。 このフラグは、透明な領域を再描画 DC を要求している場合、オブジェクトで使用する必要があります。  
  
- **OLEDC_OFFSCREEN**に画面にコピーする必要がありますし、あるオフスクリーン ビットマップにレンダリングしようとして、オブジェクト コンテナーに通知します。 オブジェクトを実行しようとしている描画の処理は、画面がちらつくを生成するときに、このフラグを使用する必要があります。 コンテナーはこの要求を優先するかにできます。 ただし、このフラグが設定されていない場合、コンテナー必要があります送り返す、画面に表示される DC です。 これにより、選択範囲を表示するような直接画面操作を実行するオブジェクト (を使用して、 **XOR**操作)。  
  
### <a name="return-value"></a>戻り値  
 コンテナーのディスプレイ デバイス コンテキストへのポインター`CWnd`クライアント領域かどうか成功。 それ以外の場合、戻り値は、 **NULL**します。 ディスプレイ デバイス コンテキストは、コンテナーのウィンドウのクライアント領域に描画する以降の GDI 関数で使用できます。  
  
### <a name="remarks"></a>コメント  
 [ReleaseDC](#releasedc)描画後にコンテキストを解放するメンバー関数を呼び出す必要があります。 呼び出すときに`GetDC`オブジェクトが、独自のクライアント座標に描画する四角形を渡します。 `GetDC`コンテナーのクライアント領域の座標に平行移動します。 オブジェクトは、必要な描画する四角形のうちサイズを取得できます独自のクライアント領域四角よりも大きいをリクエストしないように[GetClientRect](#getclientrect)します。 これにより、オブジェクトが誤って描画位置がすることはできません。  
  
##  <a name="a-namegetenableda--colecontrolgetenabled"></a><a name="getenabled"></a>COleControl::GetEnabled  
 コントロールのストック Enabled プロパティの Get 機能を実装します。  
  
```  
BOOL GetEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールが有効な場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="a-namegetextendedcontrola--colecontrolgetextendedcontrol"></a><a name="getextendedcontrol"></a>COleControl::GetExtendedControl  
 プロパティの拡張のセットを持つコントロールを表すコンテナーによって管理されるオブジェクトへのポインターを取得します。  
  
```  
LPDISPATCH GetExtendedControl();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーへのポインターには、コントロール オブジェクトを拡張します。 使用可能なオブジェクトがない場合、値は、 **NULL**します。  
  
 このオブジェクトを使って操作がその`IDispatch`インターフェイスです。 使用することも`QueryInterface`オブジェクトによって提供されるその他の使用可能なインターフェイスを取得します。 ただし、オブジェクトは、特定の一連のインターフェイスをサポートするためには不要です。 他の任意のコンテナー コントロールの移植性に制限するコンテナーの拡張コントロール オブジェクトの特定の機能に依存することに注意してください。  
  
### <a name="remarks"></a>コメント  
 この関数で呼び出される関数は、オブジェクトを終了すると、ポインターを解放する必要があります。 このオブジェクトをサポートするために、コンテナーが必要ないことに注意してください。  
  
##  <a name="a-namegetfocusa--colecontrolgetfocus"></a><a name="getfocus"></a>COleControl::GetFocus  
 指定するかどうか、`COleControl`オブジェクトにフォーカスします。  
  
```  
CWnd* GetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールがアクティブでウィンドウの場合は、返す**この**コントロールがキーボード フォーカス (ようにコントロールのコンテナーによって決定されます) を持っている場合または**NULL**フォーカスがあるない場合。  
  
 それ以外の場合、取得、 `CWnd` 、フォーカスのあるオブジェクト (と同じ`CWnd::GetFocus`)。  
  
### <a name="remarks"></a>コメント  
 アクティブなウィンドウなしのコントロールがフォーカスを受け取ったときに[SetFocus](#setfocus)が呼び出されます。  
  
##  <a name="a-namegetfonta--colecontrolgetfont"></a><a name="getfont"></a>COleControl::GetFont  
 ストック フォント プロパティの Get 機能を実装します。  
  
```  
LPFONTDISP GetFont();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのストック フォント プロパティのフォントのディスパッチ インターフェイスへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し元が完了すると、オブジェクトを解放する必要があることに注意してください。 コントロールの実装内で使用して`InternalGetFont`コントロールのストックのフォント オブジェクトにアクセスします。 コントロールでフォントの使い方の詳細については、記事を参照してください。 [ActiveX コントロール: ActiveX コントロールのフォントの使用](../../mfc/mfc-activex-controls-using-fonts.md)します。  
  
##  <a name="a-namegetfonttextmetricsa--colecontrolgetfonttextmetrics"></a><a name="getfonttextmetrics"></a>COleControl::GetFontTextMetrics  
 いずれかのテキストのメトリックを測定`CFontHolder`コントロールが所有するオブジェクト。  
  
```  
void GetFontTextMetrics(
    LPTEXTMETRIC lptm,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>パラメーター  
 `lptm`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体。  
  
 `fontHolder`  
 参照、 [CFontHolder](../../mfc/reference/cfontholder-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このようなフォントを選択できます、 [COleControl::SelectFontObject](#selectfontobject)関数です。 `GetFontTextMetrics`初期化されます、`TEXTMETRIC`構造体を指す`lptm`メトリックの有効な情報を`fontHolder`のフォントが成功した場合、または成功しなかった場合はゼロで構造体に格納します。 代わりにこの関数を使用する必要があります[GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941)メタファイルに描画するときに必要な埋め込み OLE オブジェクトと同様に、コントロールがあるので、コントロールを描画します。  
  
 `TEXTMETRIC`構造の既定のフォントが更新されるときに、 [SelectFontObject](#selectfontobject)関数が呼び出されます。 呼び出す必要があります`GetFontTextMetrics`が有効では提供情報を保証するためにストック フォント プロパティを選択後にのみです。  
  
##  <a name="a-namegetforecolora--colecontrolgetforecolor"></a><a name="getforecolor"></a>COleControl::GetForeColor  
 ストックの前景色プロパティの Get 機能を実装します。  
  
```  
OLE_COLOR GetForeColor();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値として現在前景色を指定する、 **OLE_COLOR**正常終了した場合の値します。 この値に変換できる、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)への呼び出しで値`TranslateColor`です。  
  
##  <a name="a-namegethwnda--colecontrolgethwnd"></a><a name="gethwnd"></a>COleControl::GetHwnd  
 ストック hWnd プロパティの Get 機能を実装します。  
  
```  
OLE_HANDLE GetHwnd();
```  
  
### <a name="return-value"></a>戻り値  
 OLE コントロールのウィンドウのハンドルが存在する場合です。それ以外の場合**NULL**します。  
  
##  <a name="a-namegetmessagestringa--colecontrolgetmessagestring"></a><a name="getmessagestring"></a>COleControl::GetMessageString  
 識別されるメニュー項目の目的を説明する短い文字列を取得するためにフレームワークによって呼び出される`nID`です。  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 メニュー項目の id。  
  
 `rMessage`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)文字列を返されるオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 メニュー項目が強調表示された状態のステータス バーに表示するメッセージを取得するために使用できます。 既定の実装で指定された文字列リソースを読み込もうと`nID`です。  
  
##  <a name="a-namegetnotsupporteda--colecontrolgetnotsupported"></a><a name="getnotsupported"></a>COleControl::GetNotSupported  
 ユーザーがコントロールのプロパティの値にアクセスできなくなります。  
  
```  
void GetNotSupported();
```  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザーによるプロパティの取得がサポートされていない任意のプロパティの Get 関数の代わりにこの関数を呼び出します。 1 つの例には、書き込み専用であるプロパティがあります。  
  
##  <a name="a-namegetreadystatea--colecontrolgetreadystate"></a><a name="getreadystate"></a>COleControl::GetReadyState  
 コントロールの準備状態を返します。  
  
```  
long GetReadyState();
```  
  
### <a name="return-value"></a>戻り値  
 次の値のいずれかのコントロールの準備状態:  
  
 **READYSTATE_UNINITIALIZED**  
 既定の初期化状態  
  
 **READYSTATE_LOADING**  
 コントロールには、そのプロパティが現在読み込んでください。  
  
 **READYSTATE_LOADED**  
 コントロールが初期化されています。  
  
 **READYSTATE_INTERACTIVE**  
 コントロールが対話型にするのには、十分なデータが非同期データがまだ読み込まれています。  
  
 `READYSTATE_COMPLETE`  
 コントロールにそのすべてのデータがあります。  
  
### <a name="remarks"></a>コメント  
 ほとんどの単純なコントロールを区別する必要はありません**LOADED**と`INTERACTIVE`です。 ただし、データ パスのプロパティをサポートするコントロールは、少なくともいくらかのデータを非同期的に受信するまで対話型にする準備ができていない可能性があります。 コントロールは、できるだけ早く対話可能になるを試みます。  
  
##  <a name="a-namegetrectincontainera--colecontrolgetrectincontainer"></a><a name="getrectincontainer"></a>COleControl::GetRectInContainer  
 デバイス単位で表される、コンテナーを基準として、コントロールの四角形の座標を取得します。  
  
```  
BOOL GetRectInContainer(LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 コントロールの座標がコピーされる四角形の構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 コントロールが、インプレースが有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 四角形では、有効なは、コントロールがアクティブである場合のみです。  
  
##  <a name="a-namegetstocktextmetricsa--colecontrolgetstocktextmetrics"></a><a name="getstocktextmetrics"></a>COleControl::GetStockTextMetrics  
 コントロールのストック フォント プロパティで選択された状態のテキストのメトリックを測定、 [SelectStockFont](#selectstockfont)関数です。  
  
```  
void GetStockTextMetrics(LPTEXTMETRIC lptm);
```  
  
### <a name="parameters"></a>パラメーター  
 `lptm`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/dd145132)構造体。  
  
### <a name="remarks"></a>コメント  
 `GetStockTextMetrics`関数が初期化、`TEXTMETRIC`構造体を指す`lptm`有効なメトリックについては、成功した場合、または塗りつぶしを&0; 以外の場合で、構造とします。 代わりにこの関数を使用して[GetTextMetrics](http://msdn.microsoft.com/library/windows/desktop/dd144941)メタファイルに描画するときに必要な埋め込み OLE オブジェクトと同様に、コントロールがあるので、コントロールを描画します。  
  
 `TEXTMETRIC`構造の既定のフォントが更新されるときに、`SelectStockFont`関数が呼び出されます。 有効なが提供情報を保証するためにストックのフォントを選択してから、この関数を呼び出す必要があります。  
  
##  <a name="a-namegettexta--colecontrolgettext"></a><a name="gettext"></a>COleControl::GetText  
 テキストまたはキャプションのストック プロパティの Get 機能を実装します。  
  
```  
BSTR GetText();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのテキスト文字列または文字列が存在しない場合、長さ&0; の文字列の現在の値。  
  
> [!NOTE]
>  詳細については、`BSTR`データ型を参照してください[データ型](../../mfc/reference/data-types-mfc.md)マクロとグローバルに記載します。  
  
### <a name="remarks"></a>コメント  
 この関数の呼び出し元が呼び出す必要のあるメモ`SysFreeString`文字列が返されるため、無料リソース。 コントロールの実装内で使用して`InternalGetText`コントロールのテキストまたはキャプション ストック プロパティにアクセスします。  
  
##  <a name="a-namegetwindowlessdroptargeta--colecontrolgetwindowlessdroptarget"></a><a name="getwindowlessdroptarget"></a>COleControl::GetWindowlessDropTarget  
 オーバーライド`GetWindowlessDropTarget`OLE の対象となるウィンドウなしのコントロールの場合、ドラッグ アンド ドロップ操作します。  
  
```  
virtual IDropTarget* GetWindowlessDropTarget();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトへのポインター`IDropTarget`インターフェイスです。 ウィンドウなしのオブジェクトを登録できません、ウィンドウがないため、`IDropTarget`インターフェイスです。 ただし、ドラッグ アンド ドロップに参加するにウィンドウなしのオブジェクトもインターフェイスを実装してでそれを返す`GetWindowlessDropTarget`します。  
  
### <a name="remarks"></a>コメント  
 通常、このコントロールのウィンドウがドロップ先として登録されている必要があります。 コンテナーがドロップ先として、独自のウィンドウを使用して、コントロールに、独自のウィンドウがあるないためです。 コントロールがの実装を提供しなければならないだけで、`IDropTarget`インターフェイスをコンテナーは、適切なタイミングで呼び出しを委任できます。 例:  
  
 [!code-cpp[NVC_MFCAxCtl&#2;](../../mfc/reference/codesnippet/cpp/colecontrol-class_3.cpp)]  
  
##  <a name="a-nameinitializeiidsa--colecontrolinitializeiids"></a><a name="initializeiids"></a>COleControl::InitializeIIDs  
 コントロールを使用して、Iid の基本クラスを通知します。  
  
```  
void InitializeIIDs(
    const IID* piidPrimary,
    const IID* piidEvents);
```  
  
### <a name="parameters"></a>パラメーター  
 *piidPrimary*  
 コントロールの主なディスパッチ インターフェイスのインターフェイス ID へのポインター。  
  
 *piidEvents*  
 コントロールのイベント インターフェイスのインターフェイス ID へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、インターフェイスの Id を使用するコントロールの基本クラスを通知するコントロールのコンス トラクターを呼び出します。  
  
##  <a name="a-nameinternalgetfonta--colecontrolinternalgetfont"></a><a name="internalgetfont"></a>COleControl::InternalGetFont  
 コントロールのストック フォント プロパティにアクセスします。  
  
```  
CFontHolder& InternalGetFont();
```  
  
### <a name="return-value"></a>戻り値  
 参照、 [CFontHolder](../../mfc/reference/cfontholder-class.md)ストックのフォント オブジェクトを格納しているオブジェクト。  
  
##  <a name="a-nameinternalgettexta--colecontrolinternalgettext"></a><a name="internalgettext"></a>COleControl::InternalGetText  
 コントロールのストック テキストまたはキャプション プロパティにアクセスします。  
  
```  
const CString& InternalGetText();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのテキスト文字列への参照。  
  
##  <a name="a-nameinternalsetreadystatea--colecontrolinternalsetreadystate"></a><a name="internalsetreadystate"></a>中  
 コントロールの準備状態を設定します。  
  
```  
void InternalSetReadyState(long lNewReadyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *lNewReadyState*  
 次の値のいずれかのコントロールに対して設定する準備状態:  
  
 **READYSTATE_UNINITIALIZED**  
 既定の初期化状態  
  
 **READYSTATE_LOADING**  
 コントロールには、そのプロパティが現在読み込んでください。  
  
 **READYSTATE_LOADED**  
 コントロールが初期化されています。  
  
 **READYSTATE_INTERACTIVE**  
 コントロールが対話型にするのには、十分なデータが非同期データがまだ読み込まれています。  
  
 `READYSTATE_COMPLETE`  
 コントロールにそのすべてのデータがあります。  
  
### <a name="remarks"></a>コメント  
 ほとんどの単純なコントロールを区別する必要はありません**LOADED**と`INTERACTIVE`です。 ただし、データ パスのプロパティをサポートするコントロールは、少なくともいくらかのデータを非同期的に受信するまで対話型にする準備ができていない可能性があります。 コントロールは、できるだけ早く対話可能になるを試みます。  
  
##  <a name="a-nameinvalidatecontrola--colecontrolinvalidatecontrol"></a><a name="invalidatecontrol"></a>COleControl::InvalidateControl  
 自体を再描画するコントロールを強制します。  
  
```  
void InvalidateControl(
    LPCRECT lpRect = NULL,  
    BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 無効化するコントロールの領域へのポインター。  
  
 `bErase`  
 更新領域の背景が更新領域の処理時に消去するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`lpRect`が、 **NULL**値、コントロール全体が再描画されます。 場合`lpRect`は**NULL**、これは無効にするコントロールの四角形の部分を示します。 コントロールは、ウィンドウがないかが現在アクティブでない、四角形は無視されますとをクライアント サイトの呼び出しが行われた[IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337)メンバー関数。 代わりにこの関数を使用して`CWnd::InvalidateRect`または`InvalidateRect`です。  
  
##  <a name="a-nameinvalidatergna--colecontrolinvalidatergn"></a><a name="invalidatergn"></a>COleControl::InvalidateRgn  
 指定された領域内のコンテナー ウィンドウのクライアント領域を無効にします。  
  
```  
void InvalidateRgn(CRgn* pRgn, BOOL bErase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRgn`  
 ポインター、 [CRgn](../../mfc/reference/crgn-class.md)外側のウィンドウのクライアント座標で無効にするための OLE オブジェクトの表示領域を識別するオブジェクト。 このパラメーターは場合**NULL**、全体のオブジェクトが対象です。  
  
 `bErase`  
 無効化された領域の背景を消去するかどうかを指定します。 場合**TRUE**背景が消去されます。 場合**FALSE**、バック グラウンドは変更されません。  
  
### <a name="remarks"></a>コメント  
 コンテナー内のウィンドウなしのコントロールを再描画するために使用できます。 更新領域内の他の領域と、無効化された領域とマークされているときに描画次[WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージを送信します。  
  
 場合`bErase`は**TRUE**のどの更新領域の部分では、特定の部分だけでなく、全体の領域の背景が消去されます。  
  
##  <a name="a-nameisconvertingvbxa--colecontrolisconvertingvbx"></a><a name="isconvertingvbx"></a>COleControl::IsConvertingVBX  
 OLE コントロールの専用の読み込みを許可します。  
  
```  
BOOL IsConvertingVBX();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールが変換された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE コントロールを使用する&1; つに制御を VBX を使用するフォームに変換する、するときに OLE コントロールの読み込み用に特別のコードが必要な場合があります。 たとえば、OLE コントロールのインスタンスをロードする場合への呼び出しを必要があります[PX_Font](persistence-of-ole-controls.md#px_font)で、 `DoPropExchange`:  
  
 [!code-cpp[NVC_MFCAxCtl&#3;](../../mfc/reference/codesnippet/cpp/colecontrol-class_4.cpp)]  
  
 ただし、VBX コントロールがありませんでした Font オブジェクト。各フォントのプロパティは、個別に保存されました。 この場合は、使用すると`IsConvertingVBX`これら&2; つのケースを区別します。  
  
 [!code-cpp[NVC_MFCAxCtl&4;](../../mfc/reference/codesnippet/cpp/colecontrol-class_5.cpp)]  
  
 VBX コントロールが専用のバイナリ データを保存するかどうかは別のケースになります (でその**VBM_SAVEPROPERTY**メッセージ ハンドラー)、OLE コントロールが別の形式でそのバイナリ データを保存します。 OLE コントロールの場合との下位互換性 VBX コントロールを使用して古いマスター_キーと新しい形式の両方を読み取ることが、 `IsConvertingVBX` VBX コントロールまたは OLE コントロールの読み込み中かどうかを区別することによって機能します。  
  
 コントロールの`DoPropExchange`関数の場合、この条件を確認し、true の場合、(前の例では) などには、この変換に固有の読み込みコードを実行します。 コントロールを変換しない場合は、通常の負荷のコードを実行できます。 この機能は vbx から変換されているコントロールに適用できるだけです。  
  
##  <a name="a-nameisinvokealloweda--colecontrolisinvokeallowed"></a><a name="isinvokeallowed"></a>COleControl::IsInvokeAllowed  
 オートメーション メソッドの呼び出しを有効にします。  
  
```  
BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="return-value"></a>戻り値  
 コントロールが初期化されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークの実装の**idispatch::invoke**呼び出し**オーバーライド**場合は、特定の関数を判断する (で識別される`dispid`) 呼び出すことができます。 OLE コントロールの既定の動作は、オートメーション呼び出されるメソッドをコントロールが初期化されている場合にのみを許可するようにはただし、**オーバーライド**が仮想関数がオーバーライドするために必要な場合 (たとえば、コントロールは、オートメーション サーバーとして使用されている) 場合。 詳細については、サポート技術情報記事 Q166472 を参照してください"HOWTO: オートメーション サーバーとして OLE コントロールを使用します。"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="a-nameismodifieda--colecontrolismodified"></a><a name="ismodified"></a>COleControl::IsModified  
 コントロールの状態が変更されたかどうかを判断します。  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>戻り値  
 前回の保存後、コントロールの状態が変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プロパティに値が変更されたときに、コントロールの状態が変更されます。  
  
##  <a name="a-nameisoptimizeddrawa--colecontrolisoptimizeddraw"></a><a name="isoptimizeddraw"></a>COleControl::IsOptimizedDraw  
 コンテナーが現在の描画操作の最適化された描画をサポートするかどうかを決定します。  
  
```  
BOOL IsOptimizedDraw();
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**描画、現在の描画操作を最適化された以外の場合、コンテナーがサポートされている場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 最適化された描画がサポートされている場合、コントロール必要がある古いオブジェクトを選択 (ペン、ブラシ、フォントなど) デバイス コンテキストに描画が完了するとします。  
  
##  <a name="a-nameissubclassedcontrola--colecontrolissubclassedcontrol"></a><a name="issubclassedcontrol"></a>COleControl::IsSubclassedControl  
 Windows コントロールをサブクラス化が制御を決定するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL IsSubclassedControl();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールをサブクラス化された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数をオーバーライドして返す必要があります**TRUE**場合は、OLE コントロール Windows コントロールをサブクラス化します。  
  
##  <a name="a-nameloada--colecontrolload"></a><a name="load"></a>COleControl::Load  
 非同期的に読み込まれる既存のデータをリセットし、コントロールの非同期プロパティの新しい読み込みを開始します。  
  
```  
void Load(LPCTSTR strNewPath, CDataPathProperty& prop);
```  
  
### <a name="parameters"></a>パラメーター  
 *strNewPath*  
 非同期コントロール プロパティの絶対的な場所を参照するパスを含む文字列へのポインター。  
  
 *prop*  
 A[関数](../../mfc/reference/cdatapathproperty-class.md)非同期コントロール プロパティを実装するオブジェクト。  
  
##  <a name="a-namelockinplaceactivea--colecontrollockinplaceactive"></a><a name="lockinplaceactive"></a>COleControl::LockInPlaceActive  
 コンテナーが、コントロールを非アクティブ化するを防ぎます。  
  
```  
BOOL LockInPlaceActive(BOOL bLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `bLock`  
 **TRUE**をロックする場合は、コントロールのインプレース アクティブ状態**FALSE**ロックを解除する場合は、です。  
  
### <a name="return-value"></a>戻り値  
 ロックが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 終了時にコントロールのロック解除とコントロールのすべてのロックを組み合わせる必要があることに注意してください。 イベントを発生させるときに短い時間など、コントロールをロックする必要がありますだけです。  
  
##  <a name="a-nameonambientpropertychangea--colecontrolonambientpropertychange"></a><a name="onambientpropertychange"></a>COleControl::OnAmbientPropertyChange  
 コンテナーのアンビエント プロパティの値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispID*  
 変更されたアンビエント プロパティのディスパッチ ID または**DISPID_UNKNOWN**複数のプロパティが変更された場合。  
  
##  <a name="a-nameonappearancechangeda--colecontrolonappearancechanged"></a><a name="onappearancechanged"></a>COleControl::OnAppearanceChanged  
 ストックの外観プロパティの値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAppearanceChanged ();
```  
  
### <a name="remarks"></a>コメント  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。 既定の実装`InvalidateControl`します。  
  
##  <a name="a-nameonbackcolorchangeda--colecontrolonbackcolorchanged"></a><a name="onbackcolorchanged"></a>COleControl::OnBackColorChanged  
 ストックの BackColor プロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnBackColorChanged();
```  
  
### <a name="remarks"></a>コメント  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。 既定の実装`InvalidateControl`します。  
  
##  <a name="a-nameonborderstylechangeda--colecontrolonborderstylechanged"></a><a name="onborderstylechanged"></a>COleControl::OnBorderStyleChanged  
 ストックの BorderStyle プロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnBorderStyleChanged();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`InvalidateControl`します。  
  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonclicka--colecontrolonclick"></a><a name="onclick"></a>COleControl::OnClick  
 マウス ボタンが押されたまたは DoClick ストック メソッドが呼び出されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnClick(USHORT iButton);
```  
  
### <a name="parameters"></a>パラメーター  
 *名前*  
 マウス ボタンのインデックス。 次の値のいずれかを設定できます。  
  
- **LEFT_BUTTON**マウスの左ボタンをクリックします。  
  
- **MIDDLE_BUTTON**マウスの中央ボタンをクリックします。  
  
- **RIGHT_BUTTON**マウスの右ボタンをクリックします。  
  
### <a name="remarks"></a>コメント  
 既定の実装`COleControl::FireClick`します。  
  
 変更または既定の処理を拡張するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonclosea--colecontrolonclose"></a><a name="onclose"></a>COleControl::OnClose  
 コンテナーには、コントロールが呼び出されたときに、フレームワークによって呼び出されます**IOleControl::Close**関数です。  
  
```  
virtual void OnClose(DWORD dwSaveOption);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwSaveOption`  
 読み込み前に、オブジェクトを保存するかどうかを示すフラグです。 次の値を指定できます。  
  
- `OLECLOSE_SAVEIFDIRTY`  
  
- `OLECLOSE_NOSAVE`  
  
- `OLECLOSE_PROMPTSAVE`  
  
### <a name="remarks"></a>コメント  
 既定では、`OnClose`が変更された場合は、コントロール オブジェクトを保存し、`dwSaveOption`か`OLECLOSE_SAVEIFDIRTY`または`OLECLOSE_PROMPTSAVE`です。  
  
##  <a name="a-nameondoverba--colecontrolondoverb"></a><a name="ondoverb"></a>COleControl::OnDoVerb  
 コンテナーを呼び出すときに、フレームワークによって呼び出され、 **IOleObject::DoVerb**メンバー関数。  
  
```  
virtual BOOL OnDoVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 呼び出されるコントロール動詞のインデックス。  
  
 `lpMsg`  
 呼び出される動詞を原因となった Windows メッセージへのポインター。  
  
 `hWndParent`  
 コントロールの親ウィンドウへのハンドル。 ウィンドウ (または windows) かどうか、動詞の実行が作成`hWndParent`親として使用する必要があります。  
  
 `lpRect`  
 RECT 構造体が、コンテナーを基準として、コントロールの座標のコピー先へのポインター。  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を使用して、`ON_OLEVERB`と`ON_STDOLEVERB`メッセージ マップ エントリを適切な関数を呼び出すを判別します。  
  
 動詞の既定の処理を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameondrawa--colecontrolondraw"></a><a name="ondraw"></a>オーバライド  
 指定したデバイス コンテキストを使用して、指定された外接する四角形の OLE コントロールを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rcBounds,  
    const CRect& rcInvalid);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画が行われるデバイス コンテキスト。  
  
 `rcBounds`  
 境界線を含むコントロールの四角形領域。  
  
 `rcInvalid`  
 無効なコントロールの四角形領域。  
  
### <a name="remarks"></a>コメント  
 `OnDraw`通常として画面デバイス コンテキストを渡すことの画面表示のために呼び出されます`pDC`します。 `rcBounds`パラメーターでターゲットのデバイス コンテキスト (現在のマップ モード) の相対で四角形を識別します。 `rcInvalid`パラメーターは、実際の四角形は無効です。 場合によってはより小さな領域になります`rcBounds`します。  
  
##  <a name="a-nameondrawmetafilea--colecontrolondrawmetafile"></a><a name="ondrawmetafile"></a>COleControl::OnDrawMetafile  
 指定されたメタファイル デバイス コンテキストを使用して、指定された外接する四角形の OLE コントロールを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawMetafile(
    CDC* pDC,  
    const CRect& rcBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画が行われるデバイス コンテキスト。  
  
 `rcBounds`  
 境界線を含むコントロールの四角形領域。  
  
### <a name="remarks"></a>コメント  
 既定の実装、 [OnDraw](#ondraw)関数です。  
  
##  <a name="a-nameonedita--colecontrolonedit"></a><a name="onedit"></a>COleControl::OnEdit  
 コントロールの ui をアクティブにさせます。  
  
```  
virtual BOOL OnEdit(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 動詞を起動した Windows メッセージへのポインター。  
  
 `hWndParent`  
 コントロールの親ウィンドウへのハンドル。  
  
 `lpRect`  
 コンテナー内のコントロールによって使用される四角形へのポインター。  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これは、コントロールを呼び出すのと同じ効果`OLEIVERB_UIACTIVATE`動詞です。  
  
 この関数は、通常のハンドラー関数として使用する`ON_OLEVERB`マップ エントリのメッセージします。 これにより、コントロールの「オブジェクト」メニュー"Edit"動詞が使用可能なにします。 例:  
  
 [!code-cpp[NVC_MFCAxCtl&#5;](../../mfc/reference/codesnippet/cpp/colecontrol-class_6.cpp)]  
  
##  <a name="a-nameonenabledchangeda--colecontrolonenabledchanged"></a><a name="onenabledchanged"></a>COleControl::OnEnabledChanged  
 ストックの Enabled プロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnEnabledChanged();
```  
  
### <a name="remarks"></a>コメント  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。 既定の実装[InvalidateControl](#invalidatecontrol)します。  
  
##  <a name="a-nameonenumverbsa--colecontrolonenumverbs"></a><a name="onenumverbs"></a>COleControl::OnEnumVerbs  
 コンテナーを呼び出すときに、フレームワークによって呼び出され、 **IOleObject::EnumVerbs**メンバー関数。  
  
```  
virtual BOOL OnEnumVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppenumOleVerb`  
 ポインター、**返します**コントロールの動詞を列挙するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 動詞がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を列挙、`ON_OLEVERB`メッセージ マップ内のエントリ。  
  
 動詞の列挙の既定の方法を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameoneventadvisea--colecontroloneventadvise"></a><a name="oneventadvise"></a>COleControl::OnEventAdvise  
 イベント ハンドラーに接続されているか、OLE コントロールから切断されているときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnEventAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAdvise`  
 **TRUE**イベント ハンドラーがコントロールに接続されたことを示します。 **FALSE**イベント ハンドラーがコントロールから切り離されていることを示します。  
  
##  <a name="a-nameonfontchangeda--colecontrolonfontchanged"></a><a name="onfontchanged"></a>COleControl::OnFontChanged  
 ストック フォント プロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnFontChanged();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`COleControl::InvalidateControl`します。 コントロールが Windows コントロールをサブクラス化も既定の実装も送信、 **WM_SETFONT**メッセージをコントロールのウィンドウにします。  
  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl&6;](../../mfc/reference/codesnippet/cpp/colecontrol-class_7.cpp)]  
  
##  <a name="a-nameonforecolorchangeda--colecontrolonforecolorchanged"></a><a name="onforecolorchanged"></a>COleControl::OnForeColorChanged  
 ストックの前景色プロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnForeColorChanged();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`InvalidateControl`します。  
  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonfreezeeventsa--colecontrolonfreezeevents"></a><a name="onfreezeevents"></a>COleControl::OnFreezeEvents  
 コンテナーの呼び出し後に、フレームワークによって呼び出されます**IOleControl::FreezeEvents**します。  
  
```  
virtual void OnFreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFreeze`  
 **TRUE**場合は、コントロールのイベントの処理には、固定された以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
 イベント処理がフリーズまたはマスクされていない場合、その他の動作をする場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetcolorseta--colecontrolongetcolorset"></a><a name="ongetcolorset"></a>COleControl::OnGetColorSet  
 コンテナーを呼び出すときに、フレームワークによって呼び出され、 **IViewObject::GetColorSet**メンバー関数。  
  
```  
virtual BOOL OnGetColorSet(
    DVTARGETDEVICE* ptd,  
    HDC hicTargetDev,  
    LPLOGPALETTE* ppColorSet);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptd`  
 画像のレンダリングをターゲット デバイスへのポインター。 この値が場合**NULL**、ディスプレイ デバイスでは通常、既定のターゲット デバイスの画像を表示するか。  
  
 `hicTargetDev`  
 指定された対象デバイスの情報コンテキストを指定`ptd`します。 このパラメーターは、デバイス コンテキストを指定できますが、1 つは必ずしもはありません。 If `ptd` is **NULL**, `hicTargetDev` should also be **NULL**.  
  
 *ppColorSet*  
 使用される色のセットのコピー先の場所へのポインター。 関数は、色のセットを返さない場合**NULL**が返されます。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、有効な色のセットが返されます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナーは、OLE コントロールを描画するために必要なすべての色を取得するには、この関数を呼び出します。 コンテナーは、全体的なカラー パレットを設定する必要があります色と組み合わせて取得した色のセットを使用できます。 既定の実装**FALSE**します。  
  
 この要求に関する特別な処理を実行する関数をオーバーライドします。  
  
##  <a name="a-nameongetcontrolinfoa--colecontrolongetcontrolinfo"></a><a name="ongetcontrolinfo"></a>COleControl::OnGetControlInfo  
 コントロールのコンテナーが、コントロールの概要情報を要求したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnGetControlInfo(LPCONTROLINFO pControlInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControlInfo`  
 ポインター、 [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734)格納する構造体。  
  
### <a name="remarks"></a>コメント  
 この情報は、主に次のコントロールのニーモニック キーの説明で構成されます。 既定の実装の塗りつぶし`pControlInfo`に既定の情報です。  
  
 コントロールは、アクセス キーを処理する必要がある場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetdisplaystringa--colecontrolongetdisplaystring"></a><a name="ongetdisplaystring"></a>COleControl::OnGetDisplayString  
 識別されるプロパティの現在の値を表す文字列を取得するためにフレームワークによって呼び出される`dispid`です。  
  
```  
virtual BOOL OnGetDisplayString(
    DISPID dispid,  
    CString& strValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 `strValue`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)文字列を返されるオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 文字列が返された場合は 0 以外*strValue;*それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 コントロールに値を文字列に直接変換できないプロパティがあり、コンテナーが提供するプロパティ ブラウザーに表示されるプロパティの値をする場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetinplacemenua--colecontrolongetinplacemenu"></a><a name="ongetinplacemenu"></a>COleControl::OnGetInPlaceMenu  
 コントロールが UI がコンテナーの既存のメニューにマージするメニューが有効であるときに、フレームワークによって呼び出されます。  
  
```  
virtual HMENU OnGetInPlaceMenu();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのメニューのハンドルまたは**NULL**コントロールに [なし] がある場合。 既定の実装**NULL**します。  
  
### <a name="remarks"></a>コメント  
 OLE のリソースをマージする方法の詳細については、記事を参照してください。[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)します。  
  
##  <a name="a-nameongetnaturalextenta--colecontrolongetnaturalextent"></a><a name="ongetnaturalextent"></a>COleControl::OnGetNaturalExtent  
 コンテナーの応答として、フレームワークによって呼び出されます**IViewObjectEx::GetNaturalExtent**要求します。  
  
```  
virtual BOOL OnGetNaturalExtent(
    DWORD dwAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 オブジェクトがどのように表示されるかを指定します。 表現には、コンテンツ、アイコン、縮小表示または印刷したドキュメントが含まれます。 有効な値は、列挙体から取得されます[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)または**DVASPECT2**します。  
  
 *lindex*  
 関心のあるオブジェクトの部分。 現在は-1 は有効です。  
  
 `ptd`  
 指す、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)オブジェクトのサイズが返される対象デバイスを定義する構造体。  
  
 `hicTargetDev`  
 指定された対象デバイスの情報コンテキストを示す、`ptd`パラメーター元となるオブジェクトはデバイス メトリックを抽出し、デバイスの機能をテストします。 場合`ptd`は**NULL**、オブジェクトの値を無視する、`hicTargetDev`パラメーター。  
  
 *pExtentInfo*  
 指す、 **DVEXTENTINFO**をサイズ設定データを指定します。 **DVEXTENTINFO**構造体は。  
  
 `typedef struct  tagExtentInfo`  
  
 `{`  
  
 `UINT cb;`  
  
 `DWORD dwExtentMode;`  
  
 `SIZEL sizelProposed;`  
  
 `}   DVEXTENTINFO;`  
  
 構造体メンバー `dwExtentMode`&2; つの値のいずれかを実行できます。  
  
- **DVEXTENT_CONTENT**大きさはそのコントロールが正確に内容に合わせて (スナップ サイズ) を照会します。  
  
- **DVEXTENT_INTEGRAL** 、サイズ変更する場合は、提案されたサイズをコントロールに渡す  
  
 `psizel`  
 コントロールによって返されるデータのサイズ変更を指します。 返されるサイズ変更データは、調整されていない任意の次元の場合は-1 に設定されます。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、正常に取得およびサイズの調整それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定したサイズと拡張モードに最も近いオブジェクトの表示サイズを返す関数をオーバーライド、 **DVEXTENTINFO**構造体。 既定の実装**FALSE**サイズの調整ではありません。  
  
##  <a name="a-nameongetpredefinedstringsa--colecontrolongetpredefinedstrings"></a><a name="ongetpredefinedstrings"></a>COleControl::OnGetPredefinedStrings  
 プロパティの値を表す定義済み文字列のセットを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnGetPredefinedStrings(
    DISPID dispid,  
    CStringArray* pStringArray,  
    CDWordArray* pCookieArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 `pStringArray`  
 を格納する文字列配列では、値を返します。  
  
 `pCookieArray`  
 A`DWORD`戻り値を設定する配列。  
  
### <a name="return-value"></a>戻り値  
 要素に追加された場合は&0; 以外`pStringArray`と`pCookieArray`です。  
  
### <a name="remarks"></a>コメント  
 コントロールに文字列で表すことが可能な値の組を持つプロパティが設定されている場合は、この関数をオーバーライドします。 追加の各要素に対して`pStringArray`、対応する"cookie"要素を追加する必要があります*pCookieArray します。* これらの「クッキー」値に、フレームワークによって後で渡すことが、`COleControl::OnGetPredefinedValue`関数です。  
  
##  <a name="a-nameongetpredefinedvaluea--colecontrolongetpredefinedvalue"></a><a name="ongetpredefinedvalue"></a>COleControl::OnGetPredefinedValue  
 以前のオーバーライドによって返される定義済みの文字列のいずれかに対応する値を取得するためにフレームワークによって呼び出されます`COleControl::OnGetPredefinedStrings`します。  
  
```  
virtual BOOL OnGetPredefinedValue(
    DISPID dispid,  
    DWORD dwCookie,  
    VARIANT* lpvarOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 `dwCookie`  
 以前のオーバーライドによって返されるクッキー値`COleControl::OnGetPredefinedStrings`です。  
  
 `lpvarOut`  
 ポインター、 **VARIANT**からプロパティ値を返される構造体します。  
  
### <a name="return-value"></a>戻り値  
 値が返された場合は 0 以外`lpvarOut`。 それ以外の場合に 0 です。  
  
##  <a name="a-nameongetviewextenta--colecontrolongetviewextent"></a><a name="ongetviewextent"></a>COleControl::OnGetViewExtent  
 コンテナーの応答として、フレームワークによって呼び出されます[IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032)要求します。  
  
```  
virtual BOOL OnGetViewExtent(
    DWORD dwDrawAspect,
    LONG lindex,
    DVTARGETDEVICE* ptd,
    LPSIZEL lpsizel);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDrawAspect*  
 `DWORD`フォームまたは側面を記述するオブジェクトの表示されます。 有効な値は、列挙体から取得されます[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)または**DVASPECT2**します。  
  
 *lindex*  
 関心のあるオブジェクトの部分。 現在は –&1; は有効です。  
  
 `ptd`  
 指す、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)オブジェクトのサイズが返される対象デバイスを定義する構造体。  
  
 *lpsizel*  
 オブジェクトのサイズが返される場所を指します。  
  
### <a name="return-value"></a>戻り値  
 エクステント情報が正常に返された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールで&2; つのパスの描画を使用し、その不透明な直線および透明な部分が別のディメンションを持っている場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetviewrecta--colecontrolongetviewrect"></a><a name="ongetviewrect"></a>COleControl::OnGetViewRect  
 コンテナーの応答として、フレームワークによって呼び出されます**IViewObjectEx::GetRect**要求します。  
  
```  
virtual BOOL OnGetViewRect(DWORD dwAspect, LPRECTL pRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 `DWORD`フォームまたは側面を記述するオブジェクトの表示されます。 有効な値は、列挙体から取得されます[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)または**DVASPECT2**:  
  
- `DVASPECT_CONTENT`オブジェクト全体の外接する四角形。 オブジェクトの原点にによって返されたエクステントと同じサイズの左上隅**GetViewExtent***します。*  
  
- **DVASPECT_OPAQUE**四角形の不透明な領域を持つオブジェクトは、その四角形を返します。 他のユーザーは失敗します。  
  
- **DVASPECT_TRANSPARENT**四角形のすべての透過的なまたは不規則な部分をカバーします。  
  
 `pRect`  
 指す、 [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907)オブジェクトを描画する四角形を指定する構造体。 このパラメーターは、移動と、オブジェクトの拡大を制御します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、オブジェクトのサイズの四角形が正常に返されます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトのサイズは変換`OnGetViewRect`(既定では、画面の左上隅) 特定の位置以降にある四角形にします。 コントロールで&2; つのパスの描画を使用し、その不透明な直線および透明な部分が別のディメンションを持っている場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameongetviewstatusa--colecontrolongetviewstatus"></a><a name="ongetviewstatus"></a>COleControl::OnGetViewStatus  
 コンテナーの応答として、フレームワークによって呼び出されます**IViewObjectEx::GetViewStatus**要求します。  
  
```  
virtual DWORD OnGetViewStatus();
```  
  
### <a name="return-value"></a>戻り値  
 値の 1 つ、**な VIEWSTATUS**成功。 それ以外の場合 0 の場合、列挙体です。 値には、次の任意の組み合わせがあります。  
  
 **VIEWSTATUS_OPAQUE**  
 オブジェクトは、完全に不透明です。 このビットが設定されていない場合、オブジェクトには、透明な部分が含まれています。 このビットのみに適用されますコンテンツに関連する側面でなく`DVASPECT_ICON`または`DVASPECT_DOCPRINT`です。  
  
 **VIEWSTATUS_SOLIDBKGND**  
 オブジェクトには、純色の背景 (単色のブラシ パターンではないので構成される) があります。 このビットが意味のある場合にのみ、 **VIEWSTATUS_OPAQUE**が設定し、コンテンツに関連する側面にのみ、およびでなく`DVASPECT_ICON`または`DVASPECT_DOCPRINT`です。  
  
 **VIEWSTATUS_DVASPECTOPAQUE**  
 サポートしています**DVASPECT_OPAQUE**します。 すべて**IViewObjectEx**パラメーターは、この部分を呼び出すことができるように描画の外観を受け取るメソッドです。  
  
 **VIEWSTATUS_DVASPECTTRANSPARENT**  
 サポートしています**DVASPECT_TRANSPARENT**します。 すべて**IViewObjectEx**パラメーターは、この部分を呼び出すことができるように描画の外観を受け取るメソッドです。  
  
### <a name="remarks"></a>コメント  
 コントロールは、2 つのパスの描画を使用している場合は、この関数をオーバーライドします。 既定の実装**VIEWSTATUS_OPAQUE**します。  
  
##  <a name="a-nameonhidetoolbarsa--colecontrolonhidetoolbars"></a><a name="onhidetoolbars"></a>COleControl::OnHideToolBars  
 コントロールが非アクティブ化された UI である場合に、フレームワークによって呼び出されます。  
  
```  
virtual void OnHideToolBars();
```  
  
### <a name="remarks"></a>コメント  
 実装には、によって表示されるすべてのツールバーが非表示にする必要があります`OnShowToolbars`します。  
  
##  <a name="a-nameoninactivemousemovea--colecontroloninactivemousemove"></a><a name="oninactivemousemove"></a>COleControl::OnInactiveMouseMove  
 受信時にマウス ポインターでは、非アクティブなオブジェクトのコンテナーによって呼び出される、`WM_MOUSEMOVE`メッセージです。  
  
```  
virtual void OnInactiveMouseMove(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>パラメーター  
 `lprcBounds`  
 外接する四角形の外側のウィンドウのクライアント座標で、オブジェクトです。 オブジェクトの正確な位置とサイズ、画面上の通知と、`WM_MOUSEMOVE`メッセージを受信しました。  
  
 *x*  
 格納先ウィンドウのクライアント座標でマウスの位置の x 座標。  
  
 *y*  
 格納先ウィンドウのクライアント座標でマウスの位置の y 座標。  
  
 `dwKeyState`  
 キーボードのキーボードの修飾子キーの現在の状態を識別します。 有効な値のフラグのいずれかの組み合わせが可能**MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_BUTTON**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのクライアント座標 (ピクセル単位) を使用すると、マウス カーソルの位置を渡すことに注意してください。 これが可能にも同じ座標系では、オブジェクトの外接する四角形を渡すことによってです。  
  
##  <a name="a-nameoninactivesetcursora--colecontroloninactivesetcursor"></a><a name="oninactivesetcursor"></a>COleControl::OnInactiveSetCursor  
 受信時にマウス ポインターでは、非アクティブなオブジェクトのコンテナーによって呼び出される、`WM_SETCURSOR`メッセージです。  
  
```  
virtual BOOL OnInactiveSetCursor(
    LPCRECT lprcBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL bSetAlways);
```  
  
### <a name="parameters"></a>パラメーター  
 `lprcBounds`  
 外接する四角形の外側のウィンドウのクライアント座標で、オブジェクトです。 オブジェクトの正確な位置とサイズ、画面上の通知と、`WM_SETCURSOR`メッセージを受信しました。  
  
 *x*  
 格納先ウィンドウのクライアント座標でマウスの位置の x 座標。  
  
 *y*  
 格納先ウィンドウのクライアント座標でマウスの位置の y 座標。  
  
 *dwMouseMsg*  
 対象のマウス メッセージの識別子、`WM_SETCURSOR`が発生しました。  
  
 *bSetAlways*  
 オブジェクトが、カーソルを設定する必要があるかどうかを指定します。 場合**TRUE**場合、に、オブジェクトがカーソルを設定する必要があります**FALSE**、カーソル、カーソルを設定する義務はありませんし、返す必要があります**S_FALSE**という点です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのクライアント座標 (ピクセル単位) を使用すると、マウス カーソルの位置を渡すことに注意してください。 これが可能にも同じ座標系では、オブジェクトの外接する四角形を渡すことによってです。  
  
##  <a name="a-nameonkeydowneventa--colecontrolonkeydownevent"></a><a name="onkeydownevent"></a>COleControl::OnKeyDownEvent  
 ストックの KeyDown イベントが処理された後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnKeyDownEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 押されたキーの仮想キー コード値。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
### <a name="remarks"></a>コメント  
 コントロールが、イベントが発生した後、キーの情報へのアクセスを必要とする場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonkeypresseventa--colecontrolonkeypressevent"></a><a name="onkeypressevent"></a>COleControl::OnKeyPressEvent  
 KeyPress イベントが発生した株式の後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnKeyPressEvent(USHORT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 押されたキーの仮想キー コード値が含まれています。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
### <a name="remarks"></a>コメント  
 なお、`nChar`コンテナーによって値が変更されている可能性があります。  
  
 このイベントの発生後に通知が使用する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonkeyupeventa--colecontrolonkeyupevent"></a><a name="onkeyupevent"></a>COleControl::OnKeyUpEvent  
 ストックの KeyDown イベントが処理された後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnKeyUpEvent(
    USHORT nChar,  
    USHORT nShiftState);
```  
  
### <a name="parameters"></a>パラメーター  
 `nChar`  
 押されたキーの仮想キー コード値。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 `nShiftState`  
 次のフラグの組み合わせが含まれています。  
  
- **SHIFT_MASK**アクション中に、SHIFT キーが押されました。  
  
- **CTRL_MASK**アクション中に、CTRL キーが押されました。  
  
- **ALT_MASK**アクション中に、ALT キーが押されました。  
  
### <a name="remarks"></a>コメント  
 コントロールが、イベントが発生した後、キーの情報へのアクセスを必要とする場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonmappropertytopagea--colecontrolonmappropertytopage"></a><a name="onmappropertytopage"></a>COleControl::OnMapPropertyToPage  
 指定したプロパティの編集を実装するプロパティ ページのクラス ID を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMapPropertyToPage(
    DISPID dispid,  
    LPCLSID lpclsid,  
    BOOL* pbPageOptional);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 `lpclsid`  
 ポインター、 **CLSID**を通じてクラス ID を返される構造体します。  
  
 *pbPageOptional*  
 指定したプロパティ ページの使用は省略可能かどうかを示すインジケーターを返します。  
  
### <a name="return-value"></a>戻り値  
 クラス ID が返された場合は 0 以外`lpclsid`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 コンテナーのプロパティ ブラウザーからのコントロールのプロパティ ページを起動する方法を提供するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonmnemonica--colecontrolonmnemonic"></a><a name="onmnemonic"></a>COleControl::OnMnemonic  
 OLE コントロールのニーモニック キーが押されたことをコンテナーが検出されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnMnemonic(LPMSG pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 ニーモニック キーの押下時に生成された Windows メッセージへのポインター。  
  
##  <a name="a-nameonpropertiesa--colecontrolonproperties"></a><a name="onproperties"></a>COleControl::OnProperties  
 コントロールのプロパティの動詞は、コンテナーによって呼び出されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnProperties(
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 動詞を起動した Windows メッセージへのポインター。  
  
 `hWndParent`  
 コントロールの親ウィンドウへのハンドル。  
  
 `lpRect`  
 コンテナー内のコントロールによって使用される四角形へのポインター。  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、モーダル プロパティ ダイアログ ボックスが表示されます。  
  
 コントロールのプロパティ ページの表示が発生するのに、この関数を使用することもできます。 呼び出して、`OnProperties`のコントロールの親のハンドルを引数として関数を`hWndParent`パラメーター。 ここでの値、`lpMsg`と`lpRect`パラメーターは無視されます。  
  
##  <a name="a-nameonqueryhitpointa--colecontrolonqueryhitpoint"></a><a name="onqueryhitpoint"></a>COleControl::OnQueryHitPoint  
 コンテナーの応答として、フレームワークによって呼び出されます**IViewObjectEx::QueryHitPoint**要求します。  
  
```  
virtual BOOL OnQueryHitPoint(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG lCloseHint,
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 オブジェクトの表現方法を指定します。 有効な値は、列挙体から取得されます[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)または**DVASPECT2**します。  
  
 `pRectBounds`  
 ポインター、 `RECT` OLE コントロールのクライアント領域に外接する四角形を指定する構造体。  
  
 `ptlLoc`  
 ポインター、**ポイント**ヒットでチェックする位置を指定します。 ポイントは、OLE クライアント領域の座標で指定されます。  
  
 `lCloseHint`  
 [閉じる] をポイントするヒットがチェックを定義する距離です。  
  
 `pHitResult`  
 ヒット クエリの結果へのポインター。 次のいずれかの値です。  
  
- **値**`ptlLoc`は外部 OLE オブジェクトし、閉じられません。  
  
- **中心** *ptlLoc*イメージに近いされませんが、OLE オブジェクトの境界内にあります。 たとえば、透明な円のポイントになります**中心**します。  
  
- **HITRESULT_CLOSE** `ptlLoc`は内側または外側 OLE オブジェクトが対象となる内部オブジェクトに十分近いします。 小規模、シン、または詳細なオブジェクトは、この値を使用ことがあります。 その場合でも、オブジェクトの四角形、ポイントが境界の外側にある場合でも近い状態に (これは小さなオブジェクトをヒットするため必要)。  
  
- **この**`ptlLoc`オブジェクトのイメージ内にあります。  
  
### <a name="return-value"></a>戻り値  
 ヒット テストの結果が正常に返された場合は 0 以外。それ以外の場合 0 を返します。 ヒットは、OLE コントロールの表示領域の重複部分です。  
  
### <a name="remarks"></a>コメント  
 オブジェクトの表示する四角形に指定された点が重複して かどうかを照会する (ポイントをヒット)。 `QueryHitPoint`四角形以外のオブジェクトに対するヒット テストをオーバーライドできます。  
  
##  <a name="a-nameonqueryhitrecta--colecontrolonqueryhitrect"></a><a name="onqueryhitrect"></a>COleControl::OnQueryHitRect  
 コンテナーの応答として、フレームワークによって呼び出されます**IViewObjectEx::QueryHitRect**要求します。  
  
```  
virtual BOOL OnQueryHitRect(
    DWORD dwAspect,  
    LPCRECT pRectBounds,  
    LPCRECT prcLoc,  
    LONG lCloseHint,  
    DWORD* pHitResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwAspect`  
 オブジェクトがどのように表示されるかを指定します。 有効な値は、列挙体から取得されます[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)または**DVASPECT2**します。  
  
 `pRectBounds`  
 ポインター、 `RECT` OLE コントロールのクライアント領域に外接する四角形を指定する構造体。  
  
 *prcLoc*  
 ポインター、`RECT`ヒット (が重複しているオブジェクトの四角形)、オブジェクトの左上隅に対して相対的でチェックする四角形を指定する構造体。  
  
 `lCloseHint`  
 使用しません。  
  
 `pHitResult`  
 ヒット クエリの結果へのポインター。 次のいずれかの値です。  
  
- **値**OLE オブジェクトで、四角形内ポイントがヒットしません。  
  
- **この**四角形内の少なくとも&1; つのポイントは、オブジェクトのヒットになります。  
  
### <a name="return-value"></a>戻り値  
 ヒット テストの結果が正常に返された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトの表示する四角形 (四角形をヒットして) 任意の場所で指定された四角形が重複して かどうかを照会します。 `QueryHitRect`四角形以外のオブジェクトに対するヒット テストをオーバーライドできます。  
  
##  <a name="a-nameonrenderdataa--colecontrolonrenderdata"></a><a name="onrenderdata"></a>COleControl::OnRenderData  
 指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定の形式は、コントロールを使用してオブジェクトに既に配置、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)または[DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata)のメンバー関数のレンダリングを遅延のためです。 この関数の既定の実装を呼び出す`OnRenderFileData`または`OnRenderGlobalData`、それぞれ、指定されたストレージ メディアのファイルまたはメモリ場合。 要求された形式の場合`CF_METAFILEPICT`永続的なプロパティは、書式を設定または、既定の実装が適切なデータを表示し、0 以外を返します。 それ以外の場合、0 を返し、何も行われません。  
  
 場合*tymed-> lpStgMedium*は**TYMED_NULL**、 **STGMEDIUM**割り当てられで指定された入力*tymed-> lpFormatEtc*します。 ない場合**TYMED_NULL**、 **STGMEDIUM**のデータが配置を入力する必要があります。  
  
 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 データが小さなサイズに固定と容量の場合は、オーバーライド`OnRenderGlobalData`します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。、 **FORMATETC**と**STGMEDIUM**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonrenderfiledataa--colecontrolonrenderfiledata"></a><a name="onrenderfiledata"></a>COleControl::OnRenderFileData  
 ストレージ メディア ファイルは、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `pFile`  
 指す、 [CFile](../../mfc/reference/cfile-class.md)データが表示されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定の形式は、コントロールを使用してオブジェクトに既に配置、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によって、データは、代わりにこの関数の他のバージョンのいずれかをオーバーライドすることができます。 複数のストレージ メディアを処理する場合は、オーバーライド`OnRenderData`します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。、 **FORMATETC**構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonrenderglobaldataa--colecontrolonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleControl::OnRenderGlobalData  
 指定されたストレージ メディアがグローバル メモリのときに、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `phGlobal`  
 データが返されるグローバル メモリへのハンドルへのポインター。 メモリが割り当てられていない場合、このパラメーターが指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定の形式は、コントロールを使用してオブジェクトに既に配置、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 場合`phGlobal`は**NULL**から、新規`HGLOBAL`割り当てられで返される必要があります`phGlobal`します。 それ以外の場合、`HGLOBAL`によって指定された`phGlobal`データが格納される必要があります。 内に配置するデータの量、`HGLOBAL`メモリ ブロックの現在のサイズを超えることはできません。 また、ブロックより大きなサイズに再割り当てできることはできません。  
  
 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド`OnRenderData`します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。、 **FORMATETC**構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonresetstatea--colecontrolonresetstate"></a><a name="onresetstate"></a>COleControl::OnResetState  
 コントロールのプロパティは、既定値に設定する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnResetState();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[DoPropExchange](#dopropexchange)を渡すこと、`CPropExchange`プロパティの既定値に設定するオブジェクト。  
  
 コントロールの記述者がこの OLE コントロールの初期化コードを挿入できますオーバーライドします。 この関数が呼び出されます[IPersistStream::Load](http://msdn.microsoft.com/library/windows/desktop/ms680568)または[機能として](http://msdn.microsoft.com/library/windows/desktop/ms680557)失敗した場合、または[IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234)または[IPersistStorage::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) 、いずれかの最初の呼び出しなしで呼び出される**IPersistStream::Load**または**機能として**します。  
  
##  <a name="a-nameonsetclientsitea--colecontrolonsetclientsite"></a><a name="onsetclientsite"></a>COleControl::OnSetClientSite  
 コンテナーには、コントロールが呼び出されたときに、フレームワークによって呼び出されます**IOleControl::SetClientSite**関数です。  
  
```  
virtual void OnSetClientSite();
```  
  
### <a name="remarks"></a>コメント  
 既定では、`OnSetClientSite`データ パスのプロパティを読み込むかどうかを確認し、呼び出しの場合は、`DoDataPathPropExchange`です。  
  
 この通知の特別な処理を実行する関数をオーバーライドします。 具体的には、この関数のオーバーライドは基本クラスを呼び出す必要があります。  
  
##  <a name="a-nameonsetdataa--colecontrolonsetdata"></a><a name="onsetdata"></a>COleControl::OnSetData  
 データを指定して、コントロールのデータを置き換えるため、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データの形式を指定します。  
  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが存在する構造体します。  
  
 `bRelease`  
 **TRUE**場合は、コントロールは、ストレージ メディアを解放する必要があります**FALSE**場合は、コントロールがストレージ メディアを解放する必要があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合は、データが永続的なプロパティ セット内の形式、既定の実装は、コントロールの状態を適宜変更します。 それ以外の場合、既定の実装では、何も行いません。 場合`bRelease`は**TRUE**への呼び出しでは、 **ReleaseStgMedium**になります。 それ以外の場合の not。  
  
 データを指定して、コントロールのデータを置き換えるには、この関数をオーバーライドします。  
  
 詳細については、次を参照してください。、 **FORMATETC**と**STGMEDIUM**構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonsetextenta--colecontrolonsetextent"></a><a name="onsetextent"></a>COleControl::OnSetExtent  
 コントロールの範囲は、呼び出しの結果として、変更する必要がある場合に、フレームワークによって呼び出されます[IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330)します。  
  
```  
virtual BOOL OnSetExtent(LPSIZEL lpSizeL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSizeL`  
 ポインター、**サイズ**構造体で表されるコントロールの高さと幅を表す長整数を使用する**HIMETRIC**単位です。  
  
### <a name="return-value"></a>戻り値  
 サイズの変更が受け入れられた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、コントロールのエクステントのサイズ変更を処理します。 コントロールが、インプレース アクティブ、コンテナーへの呼び出しの場合**OnPosRectChanged**が行われます。  
  
 コントロールの既定のサイズ変更を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonsetobjectrectsa--colecontrolonsetobjectrects"></a><a name="onsetobjectrects"></a>COleControl::OnSetObjectRects  
 呼び出しを実装するためにフレームワークによって呼び出される[IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767)します。  
  
```  
virtual BOOL OnSetObjectRects(
    LPCRECT lpRectPos,  
    LPCRECT lpRectClip);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectPos*  
 コントロールの新しい位置と、コンテナーとの相対サイズを示す RECT 構造体へのポインター。  
  
 `lpRectClip`  
 ポインター、`RECT`コントロールのクリッピング四角形の領域を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 位置変更が受け入れられた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、自動的にコントロール ウィンドウのサイズを変更して、位置変更を処理し、返します**TRUE**します。  
  
 この関数の既定の動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonshowtoolbarsa--colecontrolonshowtoolbars"></a><a name="onshowtoolbars"></a>COleControl::OnShowToolBars  
 コントロールの UI がアクティブになったときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnShowToolBars();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
##  <a name="a-nameontextchangeda--colecontrolontextchanged"></a><a name="ontextchanged"></a>COleControl::OnTextChanged  
 ストックのキャプションまたはテキストのプロパティ値が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnTextChanged();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装`InvalidateControl`します。  
  
 このプロパティが変更された後に通知する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonwindowlessmessagea--colecontrolonwindowlessmessage"></a><a name="onwindowlessmessage"></a>COleControl::OnWindowlessMessage  
 コンテナーの応答として、フレームワークによって呼び出されます**IOleInPlaceObjectWindowless::OnWindowMessage**要求します。  
  
```  
virtual BOOL OnWindowlessMessage(
    UINT msg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `msg`  
 Windows で渡されるメッセージの識別子です。  
  
 `wParam`  
 ように Windows によって渡されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容の値に依存、`msg`パラメーター。  
  
 `lParam`  
 ように Windows によって渡されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容の値に依存、`msg`パラメーター。  
  
 *plResult*  
 Windows の結果コード。 メッセージの処理の結果を指定し、送信メッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウなしのコントロールのウィンドウ メッセージを処理します。 `COleControl``OnWindowlessMessage`マウス メッセージと、キーボード メッセージ以外のウィンドウ メッセージを処理するために使用する必要があります。 `COleControl`提供[SetCapture](#setcapture)と[SetFocus](#setfocus)ウィンドウなしの OLE オブジェクトのマウスのキャプチャとキーボードのフォーカスを取得するには、具体的にします。  
  
 ウィンドウなしのオブジェクトは、ウィンドウを持っていないために、コンテナー メッセージをディスパッチできるようにするためのメカニズムが必要です。 ウィンドウなしの OLE オブジェクト メッセージを取得、コンテナーからを通じて、`OnWindowMessage`メソッドを`IOleInPlaceObjectWindowless`インターフェイス (の拡張機能[IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)ウィンドウなしのサポート用)。 `OnWindowMessage`受け取らない、`HWND`パラメーター。  
  
##  <a name="a-nameparenttoclienta--colecontrolparenttoclient"></a><a name="parenttoclient"></a>COleControl::ParentToClient  
 座標に変換`pPoint`クライアント座標にします。  
  
```  
virtual UINT ParentToClient(
    LPCRECT lprcBounds,
    LPPOINT pPoint,
    BOOL bHitTest = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lprcBounds`  
 コンテナー内の OLE コントロールの境界へのポインター。 クライアント領域ではなく、境界線とスクロール バーを含むコントロール全体の領域。  
  
 `pPoint`  
 親 (コンテナー) へのポインターは、コントロールのクライアント領域の座標に変換 をポイントします。  
  
 `bHitTest`  
 ヒット テストがポイントで実行するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 場合`bHitTest`は**FALSE**、返す**HTNOWHERE**します。 場合`bHitTest`は**TRUE**OLE コントロールのクライアント領域に着陸した親 (コンテナー) をポイントする場所を取得、およびヒット テスト値は、次のマウスの&1; つ。  
  
- **HTBORDER**のサイズ変更境界がないウィンドウの境界です。  
  
- **HTBOTTOM**ウィンドウの下部の水平方向の境界線にします。  
  
- **HTBOTTOMLEFT**ウィンドウの境界線の左下隅にあります。  
  
- **HTBOTTOMRIGHT**ウィンドウの枠線の右下隅にあります。  
  
- **HTCAPTION**タイトル バー領域にします。  
  
- **HTCLIENT**クライアント領域にします。  
  
- **HTERROR**画面の背景またはウィンドウ間を分ける線 (と同じ**HTNOWHERE**する点を除いて、 **DefWndProc** Windows 関数ビープ音がシステムはエラーを示します)。  
  
- **HTGROWBOX**サイズ ボックスです。  
  
- **HTHSCROLL**水平スクロール バーです。  
  
- **HTLEFT**ウィンドウの左罫線にします。  
  
- **HTMAXBUTTON**で、最大化ボタンをクリックします。  
  
- **HTMENU**メニュー領域にします。  
  
- **HTMINBUTTON**で、最小化ボタンをクリックします。  
  
- **HTNOWHERE**画面の背景またはウィンドウ間を分ける線。  
  
- **HTREDUCE**で、最小化ボタンをクリックします。  
  
- **HTRIGHT**ウィンドウの右罫線にします。  
  
- **HTSIZE**サイズ ボックスに (同じ**HTGROWBOX**)。  
  
- **HTSYSMENU**コントロールのメニューで、または子ウィンドウで [閉じる] ボタンをクリックします。  
  
- **HTTOP**ウィンドウの上部の水平方向の境界線にします。  
  
- **HTTOPLEFT**ウィンドウの境界線の左上隅にあります。  
  
- **HTTOPRIGHT**ウィンドウの枠線の右上隅にあります。  
  
- **HTTRANSPARENT**現在該当する別のウィンドウのウィンドウにします。  
  
- **HTVSCROLL**垂直スクロール バーです。  
  
- **HTZOOM**で、最大化ボタンをクリックします。  
  
### <a name="remarks"></a>コメント  
 入力時に`pPoint`親 (コンテナーの左上隅) の原点に対する相対パスです。 出力に`pPoint`(コントロールのクライアント領域の左上隅) の OLE コントロールのクライアント領域の原点に対する相対パスです。  
  
##  <a name="a-namepostmodaldialoga--colecontrolpostmodaldialog"></a><a name="postmodaldialog"></a>COleControl::PostModalDialog  
 モーダル ダイアログ ボックスが閉じられたことをコンテナーに通知します。  
  
```  
void PostModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 モーダル ダイアログ ボックスの親ウィンドウへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 任意のモーダル ダイアログ ボックスが表示された後に、この関数を呼び出します。 コンテナーがで無効になって、最上位ウィンドウを有効にするように、この関数を呼び出す必要があります`PreModalDialog`します。 この関数と対への呼び出しになる`PreModalDialog`します。  
  
##  <a name="a-namepremodaldialoga--colecontrolpremodaldialog"></a><a name="premodaldialog"></a>COleControl::PreModalDialog  
 モーダル ダイアログ ボックスが表示されるコンテナーに通知します。  
  
```  
void PreModalDialog(HWND hWndParent = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 モーダル ダイアログ ボックスの親ウィンドウへのハンドルします。  
  
### <a name="remarks"></a>コメント  
 任意のモーダル ダイアログ ボックスを表示する前に、この関数を呼び出します。 コンテナーには、すべてのトップレベル ウィンドウを無効にできるように、この関数を呼び出す必要があります。 モーダル ダイアログ ボックスが表示された後、呼び出す必要があります`PostModalDialog`します。  
  
##  <a name="a-namerecreatecontrolwindowa--colecontrolrecreatecontrolwindow"></a><a name="recreatecontrolwindow"></a>COleControl::RecreateControlWindow  
 破棄し、コントロールのウィンドウを再作成します。  
  
```  
void RecreateControlWindow();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウのスタイルを表すビットを変更する必要がある場合に必要な場合があります。  
  
##  <a name="a-namerefresha--colecontrolrefresh"></a><a name="refresh"></a>COleControl::Refresh  
 OLE コントロールの再描画を強制します。  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>コメント  
 この関数はサポート、`COleControl`更新と呼ばれる、ストック メソッドの基本クラスです。 これにより、OLE コントロールのユーザーが特定の時点でコントロールを再描画します。 このメソッドの詳細については、記事を参照してください。 [ActiveX コントロール: メソッド](../../mfc/mfc-activex-controls-methods.md)します。  
  
##  <a name="a-namereleasecapturea--colecontrolreleasecapture"></a><a name="releasecapture"></a>COleControl::ReleaseCapture  
 マウスのキャプチャを解放します。  
  
```  
BOOL ReleaseCapture();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールがマウスのキャプチャを持っている場合、キャプチャは解放されます。 それ以外の場合、この関数は、影響を与えません。  
  
##  <a name="a-namereleasedca--colecontrolreleasedc"></a><a name="releasedc"></a>COleControl::ReleaseDC  
 他のアプリケーションで使用するためのデバイス コンテキストを解放するウィンドウなしのコントロールのコンテナーのディスプレイ デバイス コンテキストを解放します。  
  
```  
int ReleaseDC(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 解放するコンテナー デバイス コンテキストを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出す必要があります`ReleaseDC`呼び出しごとに[GetDC](#getdc)します。  
  
##  <a name="a-namereparentcontrolwindowa--colecontrolreparentcontrolwindow"></a><a name="reparentcontrolwindow"></a>COleControl::ReparentControlWindow  
 コントロールの親を設定します。  
  
```  
virtual void ReparentControlWindow(
    HWND hWndOuter,  
    HWND hWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 *hWndOuter*  
 コントロールのウィンドウのハンドル。  
  
 `hWndParent`  
 新しい親ウィンドウのハンドル。  
  
### <a name="remarks"></a>コメント  
 コントロールのウィンドウの親をリセットするには、この関数を呼び出します。  
  
##  <a name="a-nameresetstockpropsa--colecontrolresetstockprops"></a><a name="resetstockprops"></a>COleControl::ResetStockProps  
 状態を初期化、 `COleControl` ストック プロパティが既定値にします。  
  
```  
void ResetStockProps();
```  
  
### <a name="remarks"></a>コメント  
 プロパティは、: 外観、BackColor、BorderStyle、キャプション、Enabled、フォント、ForeColor、hwnd の分離、およびテキスト。 ストック プロパティの説明は、次を参照してください。 [ActiveX コントロール: ストック プロパティの追加](../../mfc/mfc-activex-controls-adding-stock-properties.md)します。  
  
 使用してコントロールのバイナリの初期化のパフォーマンスを向上できる`ResetStockProps`と`ResetVersion`をオーバーライドする`COleControl::OnResetState`です。 下記の例を参照してください。 初期化の最適化の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl&#7;](../../mfc/reference/codesnippet/cpp/colecontrol-class_8.cpp)]  
  
##  <a name="a-nameresetversiona--colecontrolresetversion"></a><a name="resetversion"></a>COleControl::ResetVersion  
 指定した値にバージョン番号を初期化します。  
  
```  
void ResetVersion(DWORD dwVersionDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwVersionDefault`  
 コントロールに割り当てられるバージョン番号です。  
  
### <a name="remarks"></a>コメント  
 使用してコントロールのバイナリの初期化のパフォーマンスを向上できる`ResetVersion`と`ResetStockProps`をオーバーライドする`COleControl::OnResetState`です。 使用例を参照してください[ResetStockProps](#resetstockprops)します。 初期化の最適化の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
##  <a name="a-namescrollwindowa--colecontrolscrollwindow"></a><a name="scrollwindow"></a>COleControl::ScrollWindow  
 により、ウィンドウなしの OLE オブジェクトの画面、インプレース アクティブ イメージ内の領域をスクロールできます。  
  
```  
void ScrollWindow(
    int xAmount,
    int yAmount,
    LPCRECT lpRect = NULL,
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `xAmount`  
 水平方向のスクロールのデバイス単位の量を指定します。 このパラメーターは、左にスクロールする負の値を指定する必要があります。  
  
 `yAmount`  
 垂直方向のスクロールのデバイス単位の量を指定します。 このパラメーターは、上へスクロールする負の値を指定する必要があります。  
  
 `lpRect`  
 指す、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは格納先ウィンドウのクライアント座標での OLE オブジェクトのクライアント領域のスクロールの部分を示す RECT 構造体。 場合`lpRect`は**NULL**、全体の OLE オブジェクトのクライアント領域をスクロールします。  
  
 `lpClipRect`  
 指す、`CRect`オブジェクトまたは`RECT`クリップする四角形を指定します。 四角形の内部ピクセルだけがスクロールされたとき。 四角形の外側のビットである場合でも、`lpRect`四角形。 場合`lpClipRect`は**NULL**、スクロール四角形のクリップは実行されません。  
  
##  <a name="a-nameselectfontobjecta--colecontrolselectfontobject"></a><a name="selectfontobject"></a>COleControl::SelectFontObject  
 デバイス コンテキストにフォントを選択します。  
  
```  
CFont* SelectFontObject(
    CDC* pDC,  
    CFontHolder& fontHolder);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキスト オブジェクトへのポインター。  
  
 `fontHolder`  
 参照、 [CFontHolder](../../mfc/reference/cfontholder-class.md)を選択するフォントを表すオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 以前に選択したフォントへのポインター。 呼び出し元が使用するすべての描画操作を完了すると*fontHolder、*へのパラメーターとして渡すことによって以前に選択したフォントがもう一度選択する必要があります[:selectobject](../../mfc/reference/cdc-class.md#selectobject)します。  
  
##  <a name="a-nameselectstockfonta--colecontrolselectstockfont"></a><a name="selectstockfont"></a>それ  
 デバイス コンテキストには、ストック フォント プロパティを選択します。  
  
```  
CFont* SelectStockFont(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 フォントの選択をデバイス コンテキスト。  
  
### <a name="return-value"></a>戻り値  
 以前に選択したへのポインター`CFont`オブジェクトです。 使用する必要があります[:selectobject](../../mfc/reference/cdc-class.md#selectobject)が完了したら、デバイス コンテキストにこのフォントを選択します。  
  
##  <a name="a-nameserializeextenta--colecontrolserializeextent"></a><a name="serializeextent"></a>COleControl::SerializeExtent  
 シリアル化またはコントロールに割り当てられている表示領域の状態を初期化します。  
  
```  
void SerializeExtent(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`をシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 使用してコントロールのバイナリの永続化のパフォーマンスを向上できる`SerializeExtent`、 `SerializeStockProps`、および`SerializeVersion`をオーバーライドする**COleControl::Serialize**します。 下記の例を参照してください。 初期化の最適化の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl&#8;](../../mfc/reference/codesnippet/cpp/colecontrol-class_9.cpp)]  
  
##  <a name="a-nameserializestockpropsa--colecontrolserializestockprops"></a><a name="serializestockprops"></a>COleControl::SerializeStockProps  
 シリアル化または初期化の状態、 `COleControl` ストック プロパティ: 外観、背景色、BorderStyle、キャプション、Enabled、フォント、ForeColor、およびテキスト。  
  
```  
void SerializeStockProps(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`をシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ストック プロパティの説明は、次を参照してください。 [ActiveX コントロール: ストック プロパティの追加](../../mfc/mfc-activex-controls-adding-stock-properties.md)します。  
  
 使用してコントロールのバイナリの永続化のパフォーマンスを向上できる`SerializeStockProps`、 `SerializeExtent`、および`SerializeVersion`をオーバーライドする**COleControl::Serialize**します。 例については、あるコードを参照してください。 [SerializeExtent](#serializeextent)します。 初期化の最適化の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
##  <a name="a-nameserializeversiona--colecontrolserializeversion"></a><a name="serializeversion"></a>COleControl::SerializeVersion  
 シリアル化またはコントロールのバージョン情報の状態を初期化します。  
  
```  
DWORD SerializeVersion(
    CArchive& ar,
    DWORD dwVersionDefault,
    BOOL bConvert = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 A`CArchive`をシリアル化するオブジェクト。  
  
 `dwVersionDefault`  
 コントロールの現在のバージョン番号。  
  
 `bConvert`  
 保存すると、または読み込まれた時と同じ形式で保持されると、永続的なデータを最新の形式に変換する必要があるかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 コントロールのバージョン番号。 指定したアーカイブを読み込んでいる場合`SerializeVersion`アーカイブから読み込んだバージョンを返します。 それ以外の場合、現在読み込まれているバージョンを返します。  
  
### <a name="remarks"></a>コメント  
 使用してコントロールのバイナリの永続化のパフォーマンスを向上できる`SerializeVersion`、 `SerializeExtent`、および`SerializeStockProps`をオーバーライドする**COleControl::Serialize**します。 例については、あるコードを参照してください。 [SerializeExtent](#serializeextent)します。 初期化の最適化の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
##  <a name="a-namesetappearancea--colecontrolsetappearance"></a><a name="setappearance"></a>COleControl::SetAppearance  
 コントロールのストックの外観プロパティの値を設定します。  
  
```  
void SetAppearance (short sAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 *sAppearance*  
 A**短い**( `VT_I2`) コントロールの外観に使用する値。 値 0 がフラットにコントロールの外観を設定し、値 1 がコントロールの外観を 3D に設定します。  
  
### <a name="remarks"></a>コメント  
 ストック プロパティの詳細について「 [ActiveX コントロール: プロパティ](../../mfc/mfc-activex-controls-properties.md)します。  
  
##  <a name="a-namesetbackcolora--colecontrolsetbackcolor"></a><a name="setbackcolor"></a>COleControl::SetBackColor  
 コントロールのストック BackColor プロパティ値を設定します。  
  
```  
void SetBackColor(OLE_COLOR dwBackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwBackColor*  
 **OLE_COLOR**については、コントロールの描画に使用する値。  
  
### <a name="remarks"></a>コメント  
 このプロパティおよびその他の使用に関する詳細については、プロパティを関連、記事を参照してください。 [ActiveX コントロール: プロパティ](../../mfc/mfc-activex-controls-properties.md)します。  
  
##  <a name="a-namesetborderstylea--colecontrolsetborderstyle"></a><a name="setborderstyle"></a>COleControl::SetBorderStyle  
 コントロールのストック BorderStyle プロパティ値を設定します。  
  
```  
void SetBorderStyle(short sBorderStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *sBorderStyle*  
 新しいコントロールの境界線のスタイル0 境界線なし、1 は通常の境界線を示します。  
  
### <a name="remarks"></a>コメント  
 コントロールのウィンドウが再作成すると`OnBorderStyleChanged`と呼ばれます。  
  
##  <a name="a-namesetcapturea--colecontrolsetcapture"></a><a name="setcapture"></a>COleControl::SetCapture  
 コントロールの代わりにマウスのキャプチャを所有している、実行するコントロールのコンテナーのウィンドウが発生します。  
  
```  
CWnd* SetCapture();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 **CWnd**マウス入力を既に受信したウィンドウ オブジェクト。  
  
### <a name="remarks"></a>コメント  
 コントロールがアクティブでウィンドウの場合は、この関数は、コントロールの代わりにマウスのキャプチャを所有している、実行するコントロールのコンテナーのウィンドウをさせます。 それ以外の場合、この関数は、コントロール自体をマウスのキャプチャを受け取る (と同じ`CWnd::SetCapture`)。  
  
##  <a name="a-namesetcontrolsizea--colecontrolsetcontrolsize"></a><a name="setcontrolsize"></a>COleControl::SetControlSize  
 OLE コントロール ウィンドウのサイズを設定し、コンテナー コントロールのサイトが変更されていることを通知します。  
  
```  
BOOL SetControlSize(int cx, int cy);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 コントロールの新しい幅をピクセル単位で指定します。  
  
 `cy`  
 コントロールの新しい高さをピクセル単位で指定します。  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールのコンス トラクターで指定しないでください。  
  
 Windows のコントロールのすべての座標がコントロールの左上隅に対して相対的に、注意してください。  
  
##  <a name="a-namesetenableda--colecontrolsetenabled"></a><a name="setenabled"></a>COleControl::SetEnabled  
 ストック コントロールの Enabled プロパティの値を設定します。  
  
```  
void SetEnabled(BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnabled`  
 **TRUE**コントロールが有効になっている、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このプロパティを設定した後に**OnEnabledChange**が呼び出されます。  
  
##  <a name="a-namesetfocusa--colecontrolsetfocus"></a><a name="setfocus"></a>COleControl::SetFocus  
 コントロールの代わりに入力フォーカスを所有している、実行するコントロールのコンテナーのウィンドウが発生します。  
  
```  
CWnd* SetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 **CWnd**入力フォーカスを持っていたウィンドウ オブジェクトまたは**NULL**このようなウィンドウがない場合。  
  
### <a name="remarks"></a>コメント  
 コントロールがアクティブでウィンドウの場合は、この関数は、コントロールの代わりに入力フォーカスを所有している、実行するコントロールのコンテナーのウィンドウをさせます。 入力のフォーカスはキーボード入力をコンテナーのウィンドウに、コンテナーを呼び出す OLE オブジェクトへのすべての後続のキーボード メッセージをディスパッチする`SetFocus`です。 入力フォーカスを持っていたすべてのウィンドウでは、それが失われます。  
  
 コントロールはウィンドウなしではありません、この関数を実行すると、コントロール自体と、入力フォーカスを受け取る (と同じ`CWnd::SetFocus`)。  
  
##  <a name="a-namesetfonta--colecontrolsetfont"></a><a name="setfont"></a>COleControl::SetFont  
 コントロールのストック フォント プロパティを設定します。  
  
```  
void SetFont(LPFONTDISP pFontDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFontDisp*  
 フォントのディスパッチ インターフェイスへのポインター。  
  
##  <a name="a-namesetforecolora--colecontrolsetforecolor"></a><a name="setforecolor"></a>COleControl::SetForeColor  
 コントロールのストックの前景色プロパティ値を設定します。  
  
```  
void SetForeColor(OLE_COLOR dwForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwForeColor*  
 **OLE_COLOR**の前景、コントロールの描画に使用する値。  
  
### <a name="remarks"></a>コメント  
 このプロパティおよびその他の使用に関する詳細については、プロパティを関連、記事を参照してください。 [ActiveX コントロール: プロパティ](../../mfc/mfc-activex-controls-properties.md)します。  
  
##  <a name="a-namesetinitialdataformatsa--colecontrolsetinitialdataformats"></a><a name="setinitialdataformats"></a>COleControl::SetInitialDataFormats  
 コントロールによってサポートされるデータ形式のリストを初期化するためにフレームワークによって呼び出されます。  
  
```  
virtual void SetInitialDataFormats();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装は、2 つの形式を指定します:`CF_METAFILEPICT`し、永続的なプロパティを設定します。  
  
##  <a name="a-namesetinitialsizea--colecontrolsetinitialsize"></a><a name="setinitialsize"></a>COleControl::SetInitialSize  
 OLE コントロールのコンテナーに初めて表示したときのサイズを設定します。  
  
```  
void SetInitialSize(
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 ピクセル単位での OLE コントロールの初期の幅。  
  
 `cy`  
 ピクセル単位での OLE コントロールの初期の高さ。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールの初期サイズを設定して、コンス トラクターを呼び出します。 初期サイズは、デバイス単位、またはピクセル単位で計測されます。 この呼び出しは、コントロールのコンス トラクターで行うことをお勧めします。  
  
##  <a name="a-namesetmodifiedflaga--colecontrolsetmodifiedflag"></a><a name="setmodifiedflag"></a>COleControl::SetModifiedFlag  
 コントロールの変更済みの状態を変更します。  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bModified`  
 コントロールの新しい値には、フラグが変更されました。 **TRUE**コントロールの状態を変更されていることを示します**FALSE**コントロールの状態が保存だけであることを示します。  
  
### <a name="remarks"></a>コメント  
 呼び出しは、変更が発生するたびに、この関数は、コントロールの永続的な状態に影響します。 たとえば、永続的なプロパティの値が変更された場合、この関数を使ってを呼び出す`bModified` **TRUE**します。  
  
##  <a name="a-namesetnotpermitteda--colecontrolsetnotpermitted"></a><a name="setnotpermitted"></a>COleControl::SetNotPermitted  
 編集要求が失敗したことを示します。  
  
```  
void SetNotPermitted();
```  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すときに`BoundPropertyRequestEdit`は失敗します。 この関数は、型の例外をスロー **COleDispScodeException**設定操作が許可されていないことを示すためにします。  
  
##  <a name="a-namesetnotsupporteda--colecontrolsetnotsupported"></a><a name="setnotsupported"></a>COleControl::SetNotSupported  
 ユーザーがコントロールのプロパティの値を変更できないようにします。  
  
```  
void SetNotSupported();
```  
  
### <a name="remarks"></a>コメント  
 コントロールのユーザーがプロパティの値の変更がサポートされていない任意のプロパティの Set 関数の代わりにこの関数を呼び出します。 1 つの例には、プロパティは読み取り専用ですがあります。  
  
##  <a name="a-namesetrectincontainera--colecontrolsetrectincontainer"></a><a name="setrectincontainer"></a>COleControl::SetRectInContainer  
 デバイス単位で表される、コンテナーを基準として、コントロールの四角形の座標を設定します。  
  
```  
BOOL SetRectInContainer(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 コンテナーを基準として、コントロールの新しい座標を保持する四角形へのポインター。  
  
### <a name="return-value"></a>戻り値  
 呼び出しが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールが開いている場合、サイズを変更します。それ以外の場合、コンテナーの**OnPosRectChanged**関数が呼び出されます。  
  
##  <a name="a-namesettexta--colecontrolsettext"></a><a name="settext"></a>COleControl::SetText  
 コントロールのキャプションまたはテキスト ストック プロパティの値を設定します。  
  
```  
void SetText(LPCTSTR pszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszText`  
 文字の文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 ストックのキャプションとテキストのプロパティがどちらもマップされている同じ値に注意してください。 つまり、これらのプロパティに加えられた変更は、両方のプロパティに自動的に変更されます。 一般に、コントロールでは、ストック キャプションまたはテキスト プロパティのいずれかをサポートする必要があります。  
  
##  <a name="a-namethrowerrora--colecontrolthrowerror"></a><a name="throwerror"></a>COleControl::ThrowError  
 コントロールでエラーの発生を通知します。  
  
```  
void ThrowError(
    SCODE sc,  
    UINT nDescriptionID,  
    UINT nHelpID = -1);

 
void ThrowError(
    SCODE sc,  
    LPCTSTR pszDescription = NULL,  
    UINT nHelpID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `sc`  
 報告するステータス コードの値。 有効なコードの一覧については、記事を参照してください。 [ActiveX コントロール: 高度なトピック](../../mfc/mfc-activex-controls-advanced-topics.md)します。  
  
 `nDescriptionID`  
 報告する例外の文字列リソース ID です。  
  
 `nHelpID`  
 報告されるトピックのヘルプ ID です。  
  
 `pszDescription`  
 報告する例外の説明を含む文字列。  
  
### <a name="remarks"></a>コメント  
 この関数はのみから呼び出される Get または Set 関数内で OLE プロパティ、または OLE オートメーションのメソッドの実装のです。 それ以外の場合に発生するエラーを通知する必要がある場合は、株価のエラー イベントを発行する必要があります。  
  
##  <a name="a-nametransformcoordsa--colecontroltransformcoords"></a><a name="transformcoords"></a>COleControl::TransformCoords  
 トランス フォームの座標の間で値**HIMETRIC**単位とコンテナーのネイティブな単位です。  
  
```  
void TransformCoords(
    POINTL* lpptlHimetric,  
    POINTF* lpptfContainer,  
    DWORD flags);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpptlHimetric*  
 ポインター、 **POINTL**の座標を含む構造体**HIMETRIC**単位です。  
  
 *lpptfContainer*  
 ポインター、 **POINTF**コンテナーの単位のサイズで座標を保持します。  
  
 `flags`  
 次の値の組み合わせです。  
  
- **XFORMCOORDS_POSITION**コンテナー内の位置。  
  
- **XFORMCOORDS_SIZE**コンテナーのサイズ。  
  
- **XFORMCOORDS_HIMETRICTOCONTAINER**変換**HIMETRIC**コンテナーの単位に単位です。  
  
- **XFORMCOORDS_CONTAINERTOHIMETRIC**するコンテナーの単位に変換**HIMETRIC**単位です。  
  
### <a name="remarks"></a>コメント  
 最初の&2; つのフラグ**XFORMCOORDS_POSITION**と**XFORMCOORDS_SIZE**座標が位置またはサイズとして扱われるかどうか。 残りの&2; つのフラグは、変換の方向を示します。  
  
##  <a name="a-nametranslatecolora--colecontroltranslatecolor"></a><a name="translatecolor"></a>COleControl::TranslateColor  
 色値に変換、 **OLE_COLOR**のデータ型、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)データ型。  
  
```  
COLORREF TranslateColor(
    OLE_COLOR clrColor,  
    HPALETTE hpal = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrColor`  
 A **OLE_COLOR**データ型。 詳細については、Windows を参照してください。 [OleTranslateColor](http://msdn.microsoft.com/library/windows/desktop/ms694353)関数です。  
  
 `hpal`  
 オプションのパレットを識別するハンドルできる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 32 ビットの色の RGB (赤、緑、青) 値平面を定義するに最も近い色、`clrColor`デバイスを表すことができます。  
  
### <a name="remarks"></a>コメント  
 この関数は、ストック前景色と背景色のプロパティを変換すると便利です**COLORREF**で使用される型[CDC](../../mfc/reference/cdc-class.md)メンバー関数。  
  
##  <a name="a-namewillambientsbevalidduringloada--colecontrolwillambientsbevalidduringload"></a><a name="willambientsbevalidduringload"></a>COleControl::WillAmbientsBeValidDuringLoad  
 コントロールは、後で、永続的な状態から読み込まれるときに、ソース ファイルを既定値としてアンビエント プロパティの値を使用するかどうかを決定します。  
  
```  
BOOL WillAmbientsBeValidDuringLoad();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外では、アンビエント プロパティを有効になることを示しますそれ以外の場合アンビエント プロパティに無効になります。  
  
### <a name="remarks"></a>コメント  
 一部のコンテナーで、コントロールがない、アンビエント プロパティへのアクセスのオーバーライドの最初の呼び出し中に`COleControl::DoPropExchange`します。 これは、コンテナーを呼び出す場合、該当[IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730)または[機能として](http://msdn.microsoft.com/library/windows/desktop/ms680557)呼び出しの前に[IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) (がする場合に従いません、 **OLEMISC_SETCLIENTSITEFIRST**ステータス ビット)。  
  
##  <a name="a-namewindowproca--colecontrolwindowproc"></a><a name="windowproc"></a>COleControl::WindowProc  
 ウィンドウ プロシージャを提供する`COleControl`オブジェクトです。  
  
```  
virtual LRESULT WindowProc(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 Windows メッセージを処理するを指定します。  
  
 `wParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
 `lParam`  
 メッセージの処理で使用される追加情報を提供します。 パラメーターの値は、メッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 ディスパッチされたメッセージの戻り値。  
  
### <a name="remarks"></a>コメント  
 コントロールのメッセージ マップを通じて特定のメッセージをディスパッチするには、この関数を呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプル CIRC3](../../visual-cpp-samples.md)   
 [MFC サンプル TESTHELP](../../visual-cpp-samples.md)   
 [関数のクラス](../../mfc/reference/colepropertypage-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFontHolder クラス](../../mfc/reference/cfontholder-class.md)   
 [使ってクラス](../../mfc/reference/cpictureholder-class.md)

