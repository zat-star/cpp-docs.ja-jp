---
title: "COleControl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControl クラス"
  - "コントロール [MFC], OLE"
  - "コントロール [MFC], ウィンドウなしの"
  - "OLE コントロール, MFC"
  - "ウィンドウなしのコントロール"
  - "ウィンドウなしのコントロール, MFC"
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleControl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コントロールを開発するための強力な基本クラスです。  
  
## 構文  
  
```  
class COleControl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleControl::COleControl](../Topic/COleControl::COleControl.md)|`COleControl` オブジェクトを作成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleControl::AmbientAppearance](../Topic/COleControl::AmbientAppearance.md)|コントロールの現在の外観を取得します。|  
|[COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)|BackColor のアンビエント プロパティの値を返します。|  
|[COleControl::AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)|コンテナーで指定されたコントロールの名前を返します。|  
|[COleControl::AmbientFont](../Topic/COleControl::AmbientFont.md)|アンビエント フォントのプロパティの値を返します。|  
|[COleControl::AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)|ForeColor のアンビエント プロパティの値を返します。|  
|[COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)|コンテナーのロケール ID を返します。|  
|[COleControl::AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)|コンテナーが使用する単位の型を返します。|  
|[COleControl::AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)|グラブ ハンドルが表示される必要があるかどうかを判定します。|  
|[COleControl::AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)|ができる必要がある表示するかどうかを判定します。|  
|[COleControl::AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)|コンテナーで指定されたテキストの配置の型を返します。|  
|[COleControl::AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)|コントロールがユーザー インターフェイス アクションに応答する必要があるかどうかを判定します。|  
|[COleControl::AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)|コンテナー モードを決定します。|  
|[COleControl::BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md)|バインドされたプロパティが変更されたことをコンテナーに通知します。|  
|[COleControl::BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md)|プロパティ値を編集できるアクセス許可が必要です。|  
|[COleControl::ClientToParent](../Topic/COleControl::ClientToParent.md)|コンテナーの原点に対する点へのコントロールの原点に対する点をに変換します。|  
|[COleControl::ClipCaretRect](../Topic/COleControl::ClipCaretRect.md)|コントロールで重複したキャレットの四角形を調整します。|  
|[COleControl::ControlInfoChanged](../Topic/COleControl::ControlInfoChanged.md)|コントロールが処理するニーモニックのセットの後にこの関数を変更した呼び出します。|  
|[COleControl::DisplayError](../Topic/COleControl::DisplayError.md)|コントロールの表示は、ユーザーにエラー イベントに格納します。|  
|[COleControl::DoClick](../Topic/COleControl::DoClick.md)|`DoClick` のストック メソッドの実装。|  
|[COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)|`COleControl` のオブジェクトのプロパティをシリアル化します。|  
|[COleControl::DoSuperclassPaint](../Topic/COleControl::DoSuperclassPaint.md)|Windows コントロールからサブクラス化された OLE コントロールを再描画します。|  
|[COleControl::EnableSimpleFrame](../Topic/COleControl::EnableSimpleFrame.md)|コントロールの単純なフレームのサポートを有効にします。|  
|[COleControl::ExchangeExtent](../Topic/COleControl::ExchangeExtent.md)|コントロールの幅と高さをシリアル化します。|  
|[COleControl::ExchangeStockProps](../Topic/COleControl::ExchangeStockProps.md)|コントロールのストック プロパティをシリアル化します。|  
|[COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md)|コントロールのバージョン番号をシリアル化します。|  
|[COleControl::FireClick](../Topic/COleControl::FireClick.md)|`Click` のストック イベントを発生させます。|  
|[COleControl::FireDblClick](../Topic/COleControl::FireDblClick.md)|`DblClick` のストック イベントを発生させます。|  
|[COleControl::FireError](../Topic/COleControl::FireError.md)|`Error` のストック イベントを発生させます。|  
|[COleControl::FireEvent](../Topic/COleControl::FireEvent.md)|カスタム イベントを発生させます。|  
|[COleControl::FireKeyDown](../Topic/COleControl::FireKeyDown.md)|`KeyDown` のストック イベントを発生させます。|  
|[COleControl::FireKeyPress](../Topic/COleControl::FireKeyPress.md)|`KeyPress` のストック イベントを発生させます。|  
|[COleControl::FireKeyUp](../Topic/COleControl::FireKeyUp.md)|`KeyUp` のストック イベントを発生させます。|  
|[COleControl::FireMouseDown](../Topic/COleControl::FireMouseDown.md)|`MouseDown` のストック イベントを発生させます。|  
|[COleControl::FireMouseMove](../Topic/COleControl::FireMouseMove.md)|`MouseMove` のストック イベントを発生させます。|  
|[COleControl::FireMouseUp](../Topic/COleControl::FireMouseUp.md)|`MouseUp` のストック イベントを発生させます。|  
|[COleControl::FireReadyStateChange](../Topic/COleControl::FireReadyStateChange.md)|コントロールの準備状態が変更されたときにイベントを発生させます。|  
|[COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md)|`IPointerInactive` のインターフェイスをサポートするコントロールの既定のアクティブ化の動作は変更されます。|  
|[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)|指定されたアンビエント プロパティの値を返します。|  
|[COleControl::GetAppearance](../Topic/COleControl::GetAppearance.md)|標準的な外観のプロパティの値を返します。|  
|[COleControl::GetBackColor](../Topic/COleControl::GetBackColor.md)|BackColor の標準プロパティの値を返します。|  
|[COleControl::GetBorderStyle](../Topic/COleControl::GetBorderStyle.md)|BorderStyle の標準プロパティの値を返します。|  
|[COleControl::GetCapture](../Topic/COleControl::GetCapture.md)|ウィンドウなしのコントロール、アクティブ化されたオブジェクトにマウス キャプチャを持つかどうかを判定します。|  
|[COleControl::GetClassID](../Topic/COleControl::GetClassID.md)|OLE コントロールのクラス ID を取得します。|  
|[COleControl::GetClientOffset](../Topic/COleControl::GetClientOffset.md)|コントロールの四角形領域の左上隅とクライアント領域の左上隅の違いを取得します。|  
|[COleControl::GetClientRect](../Topic/COleControl::GetClientRect.md)|コントロールのクライアント領域のサイズを取得します。|  
|[COleControl::GetClientSite](../Topic/COleControl::GetClientSite.md)|コンテナー内の現在のクライアント サイトへのポインターのオブジェクトを照会します。|  
|[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)|コントロール フラグの設定を取得します。|  
|[COleControl::GetControlSize](../Topic/COleControl::GetControlSize.md)|OLE コントロールの位置とサイズを返します。|  
|[COleControl::GetDC](../Topic/COleControl::GetDC.md)|ウィンドウなしのコントロールのコンテナーからデバイス コンテキストを取得する手段を提供します。|  
|[COleControl::GetEnabled](../Topic/COleControl::GetEnabled.md)|標準の有効なプロパティの値を返します。|  
|[COleControl::GetExtendedControl](../Topic/COleControl::GetExtendedControl.md)|コンテナーに属する拡張コントロール オブジェクトへのポインターを取得します。|  
|[COleControl::GetFocus](../Topic/COleControl::GetFocus.md)|コントロールにフォーカスがあるかどうかを判定します。|  
|[COleControl::GetFont](../Topic/COleControl::GetFont.md)|ストック フォントのプロパティの値を返します。|  
|[COleControl::GetFontTextMetrics](../Topic/COleControl::GetFontTextMetrics.md)|`CFontHolder` のオブジェクトのメトリックを返します。|  
|[COleControl::GetForeColor](../Topic/COleControl::GetForeColor.md)|ForeColor の標準プロパティの値を返します。|  
|[COleControl::GetHwnd](../Topic/COleControl::GetHwnd.md)|標準の hWnd のプロパティの値を返します。|  
|[COleControl::GetMessageString](../Topic/COleControl::GetMessageString.md)|メニュー項目にステータス バーのテキストを指定します。|  
|[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)|ユーザーがコントロールのプロパティ値にアクセスできません。|  
|[COleControl::GetReadyState](../Topic/COleControl::GetReadyState.md)|コントロールの準備状態を返します。|  
|[COleControl::GetRectInContainer](../Topic/COleControl::GetRectInContainer.md)|コンテナーに対するコントロールの四角形を返します。|  
|[COleControl::GetStockTextMetrics](../Topic/COleControl::GetStockTextMetrics.md)|標準フォント プロパティのメトリックを返します。|  
|[COleControl::GetText](../Topic/COleControl::GetText.md)|標準のテキストまたはキャプションのプロパティの値を返します。|  
|[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)|ドラッグ アンド ドロップ操作のターゲットになるようにウィンドウなしのコントロールをオーバーライドします。|  
|[COleControl::InitializeIIDs](../Topic/COleControl::InitializeIIDs.md)|コントロールが使用する IID を基本クラスに通知します。|  
|[COleControl::InternalGetFont](../Topic/COleControl::InternalGetFont.md)|標準フォントのプロパティの `CFontHolder` のオブジェクトを返します。|  
|[COleControl::InternalGetText](../Topic/COleControl::InternalGetText.md)|標準キャプションまたはテキスト プロパティを取得します。|  
|[COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)|コントロールの準備状態を設定し、準備と状態変更イベントを発生させます。|  
|[COleControl::InvalidateControl](../Topic/COleControl::InvalidateControl.md)|再描画表示されるコントロールの領域を無効にします。|  
|[COleControl::InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)|特定の領域内のコンテナー ウィンドウのクライアント領域を無効にします。  領域のウィンドウなしのコントロールを再描画するために使用できます。|  
|[COleControl::IsConvertingVBX](../Topic/COleControl::IsConvertingVBX.md)|OLE コントロールの割り当てによって特化された読み込み。|  
|[COleControl::IsModified](../Topic/COleControl::IsModified.md)|コントロールの状態が変更したかどうかを判断します。|  
|[COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)|コンテナー サポートが現在の描画操作の描画を最適化するかどうかを示します。|  
|[COleControl::IsSubclassedControl](../Topic/COleControl::IsSubclassedControl.md)|を判断するために呼び出されるかをコントロールのサブクラス Windows コントロール。|  
|[COleControl::Load](../Topic/COleControl::Load.md)|前の非同期データをリセットし、コントロールの非同期プロパティの新しい読み込みを実行します。|  
|[COleControl::LockInPlaceActive](../Topic/COleControl::LockInPlaceActive.md)|は、コントロールがコンテナーによって非アクティブにできるかどうかを判定します。|  
|[COleControl::OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)|アンビエント プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnAppearanceChanged](../Topic/COleControl::OnAppearanceChanged.md)|標準的な外観のプロパティが変更されたときに呼び出されます。|  
|[COleControl::OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)|在庫の BackColor のプロパティが変更されたときに呼び出されます。|  
|[COleControl::OnBorderStyleChanged](../Topic/COleControl::OnBorderStyleChanged.md)|在庫の BorderStyle のプロパティが変更されたときに呼び出されます。|  
|[COleControl::OnClick](../Topic/COleControl::OnClick.md)|標準のクリックのイベントを発生させるために呼び出されます。|  
|[COleControl::OnClose](../Topic/COleControl::OnClose.md)|`IOleControl::Close` コントロールが呼び出されたことを通知します。|  
|[COleControl::OnDoVerb](../Topic/COleControl::OnDoVerb.md)|コントロールの動詞が実行された後に呼び出されます。|  
|[COleControl::OnDraw](../Topic/COleControl::OnDraw.md)|それ自体を再描画するようにコントロールが要求されたときに呼び出されます。|  
|[COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)|メタファイルのデバイス コンテキストを使用して自身を再描画するようにコントロールが要求されたときにコンテナーによって呼び出されます。|  
|[COleControl::OnEdit](../Topic/COleControl::OnEdit.md)|UI にコンテナーによって呼び出されます。OLE コントロールをアクティブにします。|  
|[COleControl::OnEnabledChanged](../Topic/COleControl::OnEnabledChanged.md)|標準の有効なプロパティが変更されたときに呼び出されます。|  
|[COleControl::OnEnumVerbs](../Topic/COleControl::OnEnumVerbs.md)|コントロールの動詞を列挙するためのコンテナーによって呼び出されます。|  
|[COleControl::OnEventAdvise](../Topic/COleControl::OnEventAdvise.md)|イベント ハンドラーがコントロールから接続または切断ときに呼び出されます。|  
|[COleControl::OnFontChanged](../Topic/COleControl::OnFontChanged.md)|標準フォント プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md)|在庫の ForeColor のプロパティが変更されたときに呼び出されます。|  
|[COleControl::OnFreezeEvents](../Topic/COleControl::OnFreezeEvents.md)|コントロールのイベントが固定されているか、またはフリーズされていないときに呼び出されます。|  
|[COleControl::OnGetColorSet](../Topic/COleControl::OnGetColorSet.md)|`IOleObject::GetColorSet` コントロールが呼び出されたことを通知します。|  
|[COleControl::OnGetControlInfo](../Topic/COleControl::OnGetControlInfo.md)|コンテナーにニーモニックの情報を提供します。|  
|[COleControl::OnGetDisplayString](../Topic/COleControl::OnGetDisplayString.md)|文字列をプロパティ値を表すために取得するために呼び出されます。|  
|[COleControl::OnGetInPlaceMenu](../Topic/COleControl::OnGetInPlaceMenu.md)|コンテナー コントロールのメニューにマージするメニューのハンドルを要求します。|  
|[COleControl::OnGetNaturalExtent](../Topic/COleControl::OnGetNaturalExtent.md)|提案されたサイズと範囲のモードに最も近いコントロールの表示サイズを取得するためにオーバーライドします。|  
|[COleControl::OnGetPredefinedStrings](../Topic/COleControl::OnGetPredefinedStrings.md)|戻り値はプロパティの値の表現を文字列。|  
|[COleControl::OnGetPredefinedValue](../Topic/COleControl::OnGetPredefinedValue.md)|定義済み文字列に対応する値を返します。|  
|[COleControl::OnGetViewExtent](../Topic/COleControl::OnGetViewExtent.md)|コントロールの表示領域のサイズを取得する \(first オーバーライドされる式の描画を有効にするために使用できます\)。|  
|[COleControl::OnGetViewRect](../Topic/COleControl::OnGetViewRect.md)|特定の位置で開始する四角形にコントロールのサイズを変換するためにオーバーライドします。|  
|[COleControl::OnGetViewStatus](../Topic/COleControl::OnGetViewStatus.md)|コントロールのビュー状態を取得するためにオーバーライドします。|  
|[COleControl::OnHideToolBars](../Topic/COleControl::OnHideToolBars.md)|コントロールが非アクティブ化された UI である場合のコンテナーによって呼び出されます。|  
|[COleControl::OnInactiveMouseMove](../Topic/COleControl::OnInactiveMouseMove.md)|コントロールにマウス ポインターのディスパッチ `WM_MOUSEMOVE` のメッセージの下にあるアクティブなコントロールのコンテナーを持つオーバーライドします。|  
|[COleControl::OnInactiveSetCursor](../Topic/COleControl::OnInactiveSetCursor.md)|コントロールにマウス ポインターのディスパッチ `WM_SETCURSOR` のメッセージの下にあるアクティブなコントロールのコンテナーを持つオーバーライドします。|  
|[COleControl::OnKeyDownEvent](../Topic/COleControl::OnKeyDownEvent.md)|標準 KeyDown イベントが発生した後に呼び出されます。|  
|[COleControl::OnKeyPressEvent](../Topic/COleControl::OnKeyPressEvent.md)|在庫の KeyPress イベントが発生した後に呼び出されます。|  
|[COleControl::OnKeyUpEvent](../Topic/COleControl::OnKeyUpEvent.md)|在庫の KeyUp イベントが発生した後に呼び出されます。|  
|[COleControl::OnMapPropertyToPage](../Topic/COleControl::OnMapPropertyToPage.md)|プロパティや編集に使用するプロパティ ページを示しています。|  
|[COleControl::OnMnemonic](../Topic/COleControl::OnMnemonic.md)|コントロールのニーモニック キーが押されたときに呼び出されます。|  
|[COleControl::OnProperties](../Topic/COleControl::OnProperties.md)|コントロールのプロパティ「」の動詞が呼び出されたときに呼び出されます。|  
|[COleControl::OnQueryHitPoint](../Topic/COleControl::OnQueryHitPoint.md)|コントロールの表示があるポイントと重複するかどうかを問い合わせるをオーバーライドします。|  
|[COleControl::OnQueryHitRect](../Topic/COleControl::OnQueryHitRect.md)|コントロールに指定した四角形の位置と重複するかどうかを問い合わせるをオーバーライドします。|  
|[COleControl::OnRenderData](../Topic/COleControl::OnRenderData.md)|指定した形式でデータを取得するために、フレームワークによって呼び出されます。|  
|[COleControl::OnRenderFileData](../Topic/COleControl::OnRenderFileData.md)|指定した形式のファイルからデータを取得するために、フレームワークによって呼び出されます。|  
|[COleControl::OnRenderGlobalData](../Topic/COleControl::OnRenderGlobalData.md)|指定した形式のグローバル メモリからデータを取得するために、フレームワークによって呼び出されます。|  
|[COleControl::OnResetState](../Topic/COleControl::OnResetState.md)|既定では、コントロールのプロパティをリセットします。|  
|[COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)|`IOleControl::SetClientSite` コントロールが呼び出されたことを通知します。|  
|[COleControl::OnSetData](../Topic/COleControl::OnSetData.md)|別の値とコントロール データを置き換えます。|  
|[COleControl::OnSetExtent](../Topic/COleControl::OnSetExtent.md)|コントロールのエクステントに変更されると呼び出されます。|  
|[COleControl::OnSetObjectRects](../Topic/COleControl::OnSetObjectRects.md)|コントロールのサイズが変更された後に呼び出されます。|  
|[COleControl::OnShowToolBars](../Topic/COleControl::OnShowToolBars.md)|コントロールがアクティブになるまで UI がある場合に呼び出されます。|  
|[COleControl::OnTextChanged](../Topic/COleControl::OnTextChanged.md)|ストック Text プロパティまたはストック Caption プロパティが変更されたときに呼び出されます。|  
|[COleControl::OnWindowlessMessage](../Topic/COleControl::OnWindowlessMessage.md)|ウィンドウなしのコントロールのプロセス ウィンドウのメッセージ \(マウスおよびキーボード メッセージ以外\)。|  
|[COleControl::ParentToClient](../Topic/COleControl::ParentToClient.md)|コントロールの原点に対する点コンテナーの原点に対する点をに変換します。|  
|[COleControl::PostModalDialog](../Topic/COleControl::PostModalDialog.md)|モーダル ダイアログ ボックスが閉じられたことをコンテナーに通知します。|  
|[COleControl::PreModalDialog](../Topic/COleControl::PreModalDialog.md)|モーダル ダイアログ ボックスを表示するようとしていることをコンテナーに通知します。|  
|[COleControl::RecreateControlWindow](../Topic/COleControl::RecreateControlWindow.md)|コントロールのウィンドウを破棄し、再作成します。|  
|[COleControl::Refresh](../Topic/COleControl::Refresh.md)|コントロールの外観の再描画が強制されます。|  
|[COleControl::ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)|リリースのマウス キャプチャ。|  
|[COleControl::ReleaseDC](../Topic/COleControl::ReleaseDC.md)|ウィンドウなしのコントロール コンテナーのディスプレイ デバイス コンテキストを解放します。|  
|[COleControl::ReparentControlWindow](../Topic/COleControl::ReparentControlWindow.md)|コントロールのウィンドウの親をリセットします。|  
|[COleControl::ResetStockProps](../Topic/COleControl::ResetStockProps.md)|既定値に初期化の `COleControl` のストック プロパティ。|  
|[COleControl::ResetVersion](../Topic/COleControl::ResetVersion.md)|特定の値にバージョン番号を初期化します。|  
|[COleControl::ScrollWindow](../Topic/COleControl::ScrollWindow.md)|ウィンドウなしのコントロールを表示する埋め込み先でアクティブなイメージ内の領域をスクロールできるようになります。|  
|[COleControl::SelectFontObject](../Topic/COleControl::SelectFontObject.md)|デバイス コンテキストにカスタム フォントのプロパティを選択します。|  
|[COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md)|デバイス コンテキストに標準フォントのプロパティを選択します。|  
|[COleControl::SerializeExtent](../Topic/COleControl::SerializeExtent.md)|コントロールの表示領域をシリアル化するか、または初期化します。|  
|[COleControl::SerializeStockProps](../Topic/COleControl::SerializeStockProps.md)|`COleControl` のストック プロパティをシリアル化するか、または初期化します。|  
|[COleControl::SerializeVersion](../Topic/COleControl::SerializeVersion.md)|コントロールのバージョン情報をシリアル化するか、または初期化します。|  
|[COleControl::SetAppearance](../Topic/COleControl::SetAppearance.md)|標準的な外観のプロパティの値を設定します。|  
|[COleControl::SetBackColor](../Topic/COleControl::SetBackColor.md)|BackColor の標準プロパティの値を設定します。|  
|[COleControl::SetBorderStyle](../Topic/COleControl::SetBorderStyle.md)|BorderStyle の標準プロパティの値を設定します。|  
|[COleControl::SetCapture](../Topic/COleControl::SetCapture.md)|コントロール コンテナー ウィンドウをコントロールのためのマウス キャプチャを所有します。|  
|[COleControl::SetControlSize](../Topic/COleControl::SetControlSize.md)|OLE コントロールの位置とサイズを設定します。|  
|[COleControl::SetEnabled](../Topic/COleControl::SetEnabled.md)|標準の有効なプロパティの値を設定します。|  
|[COleControl::SetFocus](../Topic/COleControl::SetFocus.md)|コントロール コンテナー ウィンドウをコントロールの代わりに入力フォーカスを所有します。|  
|[COleControl::SetFont](../Topic/COleControl::SetFont.md)|ストック フォントのプロパティの値を設定します。|  
|[COleControl::SetForeColor](../Topic/COleControl::SetForeColor.md)|ForeColor の標準プロパティの値を設定します。|  
|[COleControl::SetInitialSize](../Topic/COleControl::SetInitialSize.md)|コンテナーで最初に表示されたとき、OLE コントロールのサイズを設定します。|  
|[COleControl::SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)|コントロールで変更された状態が変更されます。|  
|[COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)|編集要求が失敗したことを示します。|  
|[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)|ユーザーがコントロールのプロパティ値の変更を防止できます。|  
|[COleControl::SetRectInContainer](../Topic/COleControl::SetRectInContainer.md)|コンテナーに対するコントロールの四角形を設定します。|  
|[COleControl::SetText](../Topic/COleControl::SetText.md)|標準のテキストまたはキャプションのプロパティの値を設定します。|  
|[COleControl::ThrowError](../Topic/COleControl::ThrowError.md)|OLE コントロールでエラーが発生したことが示されます。|  
|[COleControl::TransformCoords](../Topic/COleControl::TransformCoords.md)|変換は、コンテナーとコントロール間で値を調整します。|  
|[COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md)|**COLORREF** の値に **OLE\_COLOR** の値を変換します。|  
|[COleControl::WillAmbientsBeValidDuringLoad](../Topic/COleControl::WillAmbientsBeValidDuringLoad.md)|アンビエント プロパティを使用できます。コントロールに読み込むかどうかを判定します。|  
|[COleControl::WindowProc](../Topic/COleControl::WindowProc.md)|`COleControl` のオブジェクトに Windows の手順を示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleControl::DrawContent](../Topic/COleControl::DrawContent.md)|コントロールの外観を更新する必要があるときに、フレームワークによって呼び出されます。|  
|[COleControl::DrawMetafile](../Topic/COleControl::DrawMetafile.md)|メタファイルのデバイス コンテキストを使用しているときに、フレームワークによって呼び出されます。|  
|[COleControl::IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)|オートメーション メソッドの呼び出しを有効にします。|  
|[COleControl::SetInitialDataFormats](../Topic/COleControl::SetInitialDataFormats.md)|コントロールでサポートされているデータ形式のリストを初期化するために、フレームワークによって呼び出されます。|  
  
## 解説  
 `CWnd`から派生した、このクラスは、イベントの発生と機能などの OLE への追加機能の特定と Windows のウィンドウ オブジェクトのすべての機能をサポートする、メソッド、およびプロパティを継承します。  
  
 OLE コントロールは、OLE コンテナー アプリケーションに挿入され、コンテナーとイベントの発生の双方向システム使用して、コンテナーとメソッドを公開し、プロパティを通信できます。  標準 OLE コンテナーが OLE コントロールの基本的な機能だけをサポートすることに注意してください。  これらは、OLE コントロールの拡張機能をサポートできません。  イベントの発生は、コントロールでイベントが発生する特定のアクション結果としてコンテナーに送信されると発生します。  次に、コンテナーはコントロールで公開された一連のメソッドを使用して通信、および C \+\+.のメンバー関数とデータ メンバーと同様にプロパティが用意されています。  この方法は、特定のアクションが発生したときに開発者がコントロールの外観を制御したり、コンテナーに通知することができます。  
  
## ウィンドウなしのコントロール  
 OLE コントロールがウィンドウなしで使用される埋め込み先編集が有効な場合があります。  ウィンドウなしのコントロールに大きな利点があります:  
  
-   ウィンドウなしのコントロールに透明、四角形以外です  
  
-   ウィンドウなしのコントロールは、オブジェクトのインスタンスのサイズと作成の時間も短くなります  
  
 コントロールは、ウィンドウは必要ではありません。  ウィンドウが提供するサービスは一つの共有ウィンドウ \(通常はコンテナー\) とコードをディスパッチするビットで簡単に提供できます。  ウィンドウをオブジェクトのほとんど不要な問題ないとです。  
  
 ウィンドウなしのアクティベーションを使用すると、\(ウィンドウを持つ\) コンテナー コントロールの独自のウィンドウで他では、指定されたサービスを提供する必要があります。  たとえば、キーボード フォーカスを問い合わせる場合、マウス キャプチャを照会またはデバイス コンテキストを取得するのコントロール自体がコンテナーによって管理されます。これらの操作  `COleControl`[操作ウィンドウなしのメンバー関数](http://msdn.microsoft.com/ja-jp/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) コンテナーはこれらの操作を開始します。  
  
 ウィンドウなしのアクティベーションを有効にすると、コントロールの `IOleInPlaceObjectWindowless` コンテナーのデリゲートの入力メッセージはインターフェイスです \(ウィンドウなしのサポートの [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 拡張機能\)。  `COleControl` の、このインターフェイスの実装は、コントロールのメッセージ マップを通じてマウスの座標を適切に調整すると、これらのメッセージをディスパッチします。  メッセージ マップに対応するエントリを追加して通常のウィンドウのメッセージなどのメッセージを処理できます。  
  
 ウィンドウなしのコントロールで、対応する `CWnd` のメンバー関数または関連の Windows API 関数の代わりに `COleControl` のメンバー関数を常に使用する必要があります。  
  
 OLE コントロール オブジェクトは、アクティブ化、非アクティブ アクティブな遷移に必要な作業量が発生し、がある遷移の速度は"状態になっている場合にのみウィンドウを作成できます。  これが問題になる場合があります: たとえば、テキスト ボックスのグリッドを検討してください。  列を上下に cursoring 場合、各コントロールは、非アクティブな埋め込み先でアクティブにしない場合。  非アクティブ化またはアクティブな遷移の速度は直接スクロール速度に影響します。  
  
 OLE コントロールのフレームワークの開発の詳細については、" " [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md) と [:概要 MFC ActiveX コントロール プログラムの作成](../../mfc/reference/mfc-activex-control-wizard.md)を参照してください。  OLE コントロールの、ウィンドウなしのコントロールやちらつきなしのコントロールが最適化の詳細については、[MFC ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `COleControl`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [MFC のサンプル CIRC3](../../top/visual-cpp-samples.md)   
 [MFC の TESTHELP サンプル](../../top/visual-cpp-samples.md)   
 [COlePropertyPage クラス](../../mfc/reference/colepropertypage-class.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFontHolder クラス](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder クラス](../../mfc/reference/cpictureholder-class.md)