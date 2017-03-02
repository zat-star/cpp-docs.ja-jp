---
title: "CMFCMenuBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar class
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
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
ms.openlocfilehash: ab2896f5ebab0df894f70e5ddb85bae3a5e1d5af
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar クラス
ドッキングを実装するメニュー バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(`CMFCToolBar::AdjustLocations` をオーバーライドします)。|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|ツール バー ボタンのイメージの下のテキスト ラベルを表示できるかどうかを指定します。 (上書き[CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels))。|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|ツールバーの水平方向のサイズを計算します。 (上書き[CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout))。|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(`CMFCToolBar::CalcLayout` をオーバーライドします)。|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|ツールバーのボタンの高さの最大値を計算します。 (上書き[CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight))。|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|ユーザーがツールバーを閉じるかどうかを指定します。 (上書き[CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed))。|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|システムが、カスタマイズ後ツールバーを元の状態に復元できるかどうかを決定します。 (上書き[CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored))。|  
|[CMFCMenuBar::Create](#create)|メニュー コントロールを作成し、それをアタッチ、`CMFCMenuBar`オブジェクトです。|  
|[CMFCMenuBar::CreateEx](#createex)|作成、`CMFCMenuBar`追加のスタイルのオプションを含むオブジェクト。|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|初期化、`CMFCMenuBar`オブジェクトです。 受け入れる、`HMENU`パラメーターに設定されているためのテンプレートとして機能する`CMFCMenuBar`です。|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|により、**ヘルプ**コンボ ボックス、メニュー バーの右側に配置されています。|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|ポップアップ メニューの影を表示するかどうかを指定します。|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(上書き[CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize))。|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|ツール バー ボタンの幅を返します。 (上書き[CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth))。|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|リソース ファイルの元のメニューにハンドルを返します。|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|リソース ファイル内の元のメニュー リソース識別子を返します。|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|ポインターを返す、**ヘルプ**コンボ ボックス。|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|ハンドルに関連付けられているメニューを返します、`CMFCMenuBar`オブジェクトです。|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|メニュー オブジェクトの現在のグローバル フォントを取得します。|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|指定した項目のインデックスに関連付けられているツール バー ボタンを返します。|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|ツール バー ボタンの高さを返します。 (上書き[CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight))。|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|無効なメニュー項目が強調表示されているかどうかを示します。|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|罫線を拡張したボタンがツールバーに表示できるかどうかを決定します。 (上書き[CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable))。|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|無効な項目が強調表示されているかどうかを示します。|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|ポップアップ メニューの影を描画するかどうかを示します。|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|メニュー バーで最近使用したメニューのコマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|ポップアップ メニューがすべてのコマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|メニューが、短い遅延の後、すべてのコマンドを表示するかどうかを示します。|  
|[CMFCMenuBar::LoadState](#loadstate)|状態を読み込みます、`CMFCMenuBar`レジストリからのオブジェクト。|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|ユーザーがツールバーのボタンを選択したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot))。|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|フレーム ウィンドウがリソース ファイルから既定のメニューを読み込むときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand` をオーバーライドします)。|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|カスタマイズ モードにメニューがあり、ユーザーがメニュー項目のテキストを変更するときに、フレームワークによって呼び出されます。|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(`CMFCToolBar::OnToolHitTest` をオーバーライドします)。|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(`CMFCToolBar::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|カスタマイズ モードにメニューがあり、ユーザーが選択したときに、フレームワークによって呼び出されます**リセット**メニュー バーのです。|  
|[CMFCMenuBar::SaveState](#savestate)|状態を保存、`CMFCMenuBar`レジストリへのオブジェクト。|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|リソース ファイルの元のメニューを設定します。|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|MDI 子ウィンドウの表示モードが変更されたときに、フレームワークによって呼び出されます。 MDI 子ウィンドウは、最大化されている新しくまたは不要になった最大化されている、このメソッドは、メニュー バーを更新します。|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|ユーザーのメニュー ボタンを動的に作成するときに生成されるランタイム クラス情報を設定します。|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|アプリケーションのすべてのメニューのフォントを設定します。|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|メニュー バーが最近使用したメニュー コマンドを表示するかどうかを指定します。|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|メニュー バーがすべてのコマンドを表示するかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCMenuBar`クラスは、メニュー バーのドッキング機能の実装です。 閉じることができません - 常に表示されますが、ツールバーが似ています。  
  
 `CMFCMenuBar`最近使用したメニュー項目のオブジェクトの表示オプションをサポートしています。 このオプションが有効になっている場合、`CMFCMenuBar`を最初に表示に使用できるコマンドのサブセットのみが表示されます。 その後、最近使用されたコマンドは、コマンドの元のサブセットと表示されます。 さらに、ユーザーは利用可能なすべてのコマンドを表示するメニューを常に展開することができます。 このため、使用可能な各コマンドでは、常に表示するか、最近使用された場合にのみ表示するには構成されます。  
  
 使用する、`CMFCMenuBar`オブジェクト、メイン ウィンドウ フレーム オブジェクトに埋め込むことです。 処理するときに、`WM_CREATE`メッセージで、呼び出す`CMFCMenuBar::Create`または`CMFCMenuBar::CreateEx`です。 関数を作成するのに関係なくを使用するメイン フレーム ウィンドウにポインターを渡します。 ドッキング可能に呼び出すことによって[CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)します。 このメニューを呼び出すことによってドッキング[CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane)します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCMenuBar`クラスです。 この例では、ウィンドウのスタイルを設定、カスタマイズ ボタンを有効にする、ください ボックスを有効にする、ポップアップ メニューの影を有効にし、メニュー バーを更新する方法を示します。 このコード スニペットの一部である、 [IE のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 `CMFCMenuBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmenubar.h  
  
##  <a name="a-nameadjustlocationsa--cmfcmenubaradjustlocations"></a><a name="adjustlocations"></a>CMFCMenuBar::AdjustLocations  
 メニュー バーでメニュー項目の位置を調整します。  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameallowchangetextlabelsa--cmfcmenubarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFCMenuBar::AllowChangeTextLabels  
 メニュー バーでのイメージの下のテキスト ラベルを許すかどうかを示します。  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`場合は、ユーザーがイメージの下のテキスト ラベルを表示する選択できます。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameallowshowonpanemenua--cmfcmenubarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCMenuBar::AllowShowOnPaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecalcfixedlayouta--cmfcmenubarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 [入力] `bHorz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecalclayouta--cmfcmenubarcalclayout"></a><a name="calclayout"></a>CMFCMenuBar::CalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwMode`  
 [入力] `nLength`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecalcmaxbuttonheighta--cmfcmenubarcalcmaxbuttonheight"></a><a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecanbecloseda--cmfcmenubarcanbeclosed"></a><a name="canbeclosed"></a>CMFCMenuBar::CanBeClosed  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecanberestoreda--cmfcmenubarcanberestored"></a><a name="canberestored"></a>CMFCMenuBar::CanBeRestored  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecreatea--cmfcmenubarcreate"></a><a name="create"></a>CMFCMenuBar::Create  
 メニュー コントロールを作成し、それをアタッチ、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 新しい親ウィンドウへのポインター`CMFCMenuBar`オブジェクトです。  
  
 [入力] `dwStyle`  
 新しいメニュー バーのスタイル。  
  
 [入力] `nID`  
 メニュー バーの子ウィンドウの ID。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 作成した後、`CMFCMenuBar`オブジェクトを呼び出す必要があります`Create`します。 このメソッドは、作成、`CMFCMenuBar`を制御し、それを`CMFCMenuBar`オブジェクトです。  
  
 ツール バーのスタイルの詳細については、次を参照してください。 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle)します。  
  
##  <a name="a-namecreateexa--cmfcmenubarcreateex"></a><a name="createex"></a>CMFCMenuBar::CreateEx  
 作成、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)指定拡張スタイルを持つオブジェクト。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    CRect rcBorders = CRect(1,
    1,
    1,
    1),  
    UINT nID =AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 新しい親ウィンドウへのポインター`CMFCMenuBar`オブジェクトです。  
  
 [入力] `dwCtrlStyle`  
 新しいメニュー バーのスタイルを追加します。  
  
 [入力] `dwStyle`  
 新しいメニュー バーのメインのスタイル。  
  
 [入力] `rcBorders`  
 A`CRect`の境界線のサイズを指定するパラメーター、`CMFCMenuBar`オブジェクトです。  
  
 [入力] `nID`  
 メニュー バーの子ウィンドウの ID。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 代わりにこの関数を使用する必要があります[CMFCMenuBar::Create](#create)だけでなく、ツールバーのスタイルのスタイルを指定する場合。 頻繁に使用されるいくつか追加のスタイルは`TBSTYLE_TRANSPARENT`と`CBRS_TOP`です。  
  
 その他のスタイルの一覧は、次を参照してください。[ツール バー コントロールとボタンのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760439)、[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)、および[一般的なウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/ms632600)します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`CreateEx`のメソッド、`CMFCMenuBar`クラスです。 このコード スニペットの一部である、 [IE のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="a-namecreatefrommenua--cmfcmenubarcreatefrommenu"></a><a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu  
 初期化、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトです。 このメソッドのモデル、`CMFCMenuBar`オブジェクトの後に、`HMENU`パラメーター。  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
 メニュー リソースへのハンドル。 `CreateFromMenu`このリソースのテンプレートとして使用、`CMFCMenuBar`です。  
  
 [入力] `bDefaultMenu`  
 新しいメニューが既定のメニューであるかどうかを示すブール値。  
  
 [入力] `bForceUpdate`  
 このメソッドがメニュー更新を強制するかどうかを示すブール値。  
  
### <a name="remarks"></a>コメント  
 メニュー リソースと同じ、メニュー項目がメニュー コントロールが必要な場合は、このメソッドを使用します。 いずれかを呼び出した後は、このメソッドを呼び出す[CMFCMenuBar::Create](#create)または[CMFCMenuBar::CreateEx](#createex)します。  
  
##  <a name="a-nameenablehelpcomboboxa--cmfcmenubarenablehelpcombobox"></a><a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox  
 により、**ヘルプ**コンボ ボックス、メニュー バーの右側に配置されています。  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 ボタンのコマンド ID、**ヘルプ**コンボ ボックス。  
  
 [入力] `lpszPrompt`  
 空でアクティブでない場合に、フレームワークがコンボ ボックスに表示されるテキストを含む文字列です。 たとえば、「入力テキストをここで」します。  
  
 [入力] `nComboBoxWidth`  
 ピクセル単位でコンボ ボックスのボタンの幅。  
  
### <a name="remarks"></a>コメント  
 **ヘルプ**コンボ ボックスのような**ヘルプ**コンボ ボックスのメニュー バーで[!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)]します。  
  
 このメソッドを呼び出すと`uiID`を 0 に設定すると、このメソッドは、コンボ ボックス非表示にします。 それ以外の場合、このメソッドは、メニュー バーの右側にあるコンボ ボックスを自動的に表示します。 このメソッドを呼び出した後で呼び出す[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) 、挿入されたへのポインターを取得する[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)オブジェクトです。  
  
##  <a name="a-nameenablemenushadowsa--cmfcmenubarenablemenushadows"></a><a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows  
 ポップアップ メニューの影を有効にします。  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 ポップアップ メニューの影を有効にするかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用するアルゴリズムは複雑で、低速なシステム上のアプリケーションのパフォーマンスが低下する可能性があります。  
  
##  <a name="a-namegetavailableexpandsizea--cmfcmenubargetavailableexpandsize"></a><a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcolumnwidtha--cmfcmenubargetcolumnwidth"></a><a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetdefaultmenua--cmfcmenubargetdefaultmenu"></a><a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu  
 元のメニューへのハンドルを取得します。 フレームワークでは、リソース ファイルから元のメニューを読み込みます。  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースへのハンドル。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、メニューをカスタマイズする場合は、元のメニューへのハンドルを取得するこのメソッドを使用できます。  
  
##  <a name="a-namegetdefaultmenuresida--cmfcmenubargetdefaultmenuresid"></a><a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId  
 既定のメニューのリソース識別子を取得します。  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースの識別子です。  
  
### <a name="remarks"></a>コメント  
 フレームワークの既定のメニューを読み込みます、`CMFCMenuBar`リソース ファイルからのオブジェクト。  
  
##  <a name="a-namegetfloatpopupdirectiona--cmfcmenubargetfloatpopupdirection"></a><a name="getfloatpopupdirection"></a>CMFCMenuBar::GetFloatPopupDirection  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetforcedownarrowsa--cmfcmenubargetforcedownarrows"></a><a name="getforcedownarrows"></a>CMFCMenuBar::GetForceDownArrows  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegethelpcomboboxa--cmfcmenubargethelpcombobox"></a><a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox  
 ポインターを返す、**ヘルプ**コンボ ボックス。  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、**ヘルプ**コンボ ボックス。 `NULL`場合、**ヘルプ**コンボ ボックスを非表示または有効になっていません。  
  
### <a name="remarks"></a>コメント  
 **ヘルプ**メニュー バーの右側にあるコンボ ボックスを配置します。 メソッドを呼び出して[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)このコンボ ボックスを有効にします。  
  
##  <a name="a-namegethmenua--cmfcmenubargethmenu"></a><a name="gethmenu"></a>CMFCMenuBar::GetHMenu  
 接続されているメニューへのハンドルを取得、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトです。  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="a-namegetmenufonta--cmfcmenubargetmenufont"></a><a name="getmenufont"></a>CMFCMenuBar::GetMenuFont  
 現在のメニューのフォントを取得します。  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHorz`  
 水平または垂直のフォントを返すかどうかを指定するブール値パラメーター。 `TRUE`水平方向のフォントを示します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)メニュー バーの現在のフォントを含むパラメーターです。  
  
### <a name="remarks"></a>コメント  
 返されるフォントは、アプリケーションのグローバル パラメーターです。 2 つのグローバル フォントはすべてに対して保持`CMFCMenuBar`オブジェクトです。 水平および垂直方向のメニュー バーでは、これら個別のフォントが使用されます。  
  
##  <a name="a-namegetmenuitema--cmfcmenubargetmenuitem"></a><a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem  
 取得、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)項目のインデックスに基づいて、メニュー バー上のオブジェクト。  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iItem`  
 返されるメニュー項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCToolBarButton`により指定されたインデックスと一致するオブジェクト`iItem`します。 `NULL`インデックスが無効な場合です。  
  
##  <a name="a-namegetrowheighta--cmfcmenubargetrowheight"></a><a name="getrowheight"></a>CMFCMenuBar::GetRowHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetsystembuttona--cmfcmenubargetsystembutton"></a><a name="getsystembutton"></a>CMFCMenuBar::GetSystemButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiBtn`  
 [入力] `bByCommand`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetsystembuttonscounta--cmfcmenubargetsystembuttonscount"></a><a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButtonsCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetsystemmenua--cmfcmenubargetsystemmenu"></a><a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namehighlightdisableditemsa--cmfcmenubarhighlightdisableditems"></a><a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems  
 フレームワークに無効なメニュー項目が強調表示するかどうかを制御します。  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHighlight`  
 フレームワークが使用できないメニュー項目を強調表示するかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークは使用できないメニュー項目を選択しないユーザーは、上にマウス ポインターを置いたときにします。  
  
##  <a name="a-nameisbuttonextrasizeavailablea--cmfcmenubarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeAvailable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameishighlightdisableditemsa--cmfcmenubarishighlightdisableditems"></a><a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems  
 フレームワークが使用できないメニュー項目を強調表示するかどうかを示します。  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は使用できないメニュー項目が強調表示されます。それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークは使用できないメニュー項目を選択しないユーザーは、上にマウス ポインターを置いたときにします。 使用して、 [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)メソッドがこの機能を有効にします。  
  
##  <a name="a-nameismenushadowsa--cmfcmenubarismenushadows"></a><a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows  
 ポップアップ メニューの影を描画するかどうかを示します。  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニュー影を描画する場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCMenuBar::EnableMenuShadows](#enablemenushadows)メソッドを有効にするか、この機能を無効にします。  
  
##  <a name="a-nameisrecentlyusedmenusa--cmfcmenubarisrecentlyusedmenus"></a><a name="isrecentlyusedmenus"></a>CMFCMenuBar::IsRecentlyUsedMenus  
 メニュー バーで最近使用したメニューのコマンドを表示するかどうかを示します。  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CMFCMenuBar`最近使用したオブジェクトの表示 メニューのコマンド。 それ以外の場合、0 です。  
  
### <a name="remarks"></a>コメント  
 関数を使用して[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)を制御するメニュー コマンドを使用するかどうか、メニュー バーは最近に示しています。  
  
##  <a name="a-nameisshowallcommandsa--cmfcmenubarisshowallcommands"></a><a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands  
 すべてのコマンドがメニューに表示するかどうかを示します。  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CMFCMenuBar`すべてが表示されるコマンド。 それ以外の場合、0 です。  
  
### <a name="remarks"></a>コメント  
 A`CMFCMenuBar`オブジェクトは、すべてのコマンドを表示するか、コマンドのサブセットのみを表示するように構成できます。 この機能の詳細については、次を参照してください。 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)します。  
  
 `IsShowAllCommands`教えてくれるに対してこの機能をどのように構成するか、`CMFCMenuBar`オブジェクトです。 メニュー コマンドが表示されるかを制御するには、メソッドを使用[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)と[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)します。  
  
##  <a name="a-nameisshowallcommandsdelaya--cmfcmenubarisshowallcommandsdelay"></a><a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay  
 示すかどうか、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトには、短い遅延の後、すべてのコマンドが表示されます。  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーは、多少の遅延の後にすべてのメニューを表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 最近使用した表示項目をメニュー バーを構成するときに、メニュー バーには、2 つの方法のいずれかですべてのメニューが表示されます。  
  
-   遅延の後、プログラムからユーザーが、メニューの下部にある矢印にマウス カーソルを置いたときにすべてのメニューを表示します。  
  
-   ユーザーがメニューの下部にある矢印をクリックした後は、すべてのメニューを表示します。  
  
 既定では、すべて`CMFCMenuBar`オブジェクトでは、オプションを使用して、しばらく時間がかかるの後にすべてのメニューを表示します。 プログラムを使用して、このオプションを変更することはできません、`CMFCMenuBar`クラスです。 ただし、ユーザー動作を変更できますツールバーをカスタマイズするときを使用して、**カスタマイズ** ダイアログ ボックス.  
  
##  <a name="a-nameloadstatea--cmfcmenubarloadstate"></a><a name="loadstate"></a>CMFCMenuBar::LoadState  
 Windows レジストリから、メニュー バーの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 Windows レジストリ キーのパスを含む文字列です。  
  
 [入力] `nIndex`  
 メニュー バーのコントロールの ID。  
  
 [入力] `uiID`  
 予約済みの値。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCMenuBar::SaveState](#savestate)メニュー バーの状態をレジストリに保存するメソッドです。 保存されている情報には、メニュー項目には、ドッキング状態では、メニュー バーの位置が含まれます。  
  
 ほとんどの場合、アプリケーションは呼び出しません`LoadState`します。 フレームワークは、ワークスペースを初期化するときは、このメソッドを呼び出します。  
  
##  <a name="a-nameonchangehota--cmfcmenubaronchangehot"></a><a name="onchangehot"></a>CMFCMenuBar::OnChangeHot  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iHot`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondefaultmenuloadeda--cmfcmenubarondefaultmenuloaded"></a><a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded  
 フレームワークは、リソース ファイルから、メニュー リソースの読み込み時に、このメソッドを呼び出します。  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
 接続されているメニューのハンドル、`CMFCMenuBar`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 フレームワーク メニュー リソースをリソース ファイルから読み込まれた後にカスタム コードを実行するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonsendcommanda--cmfcmenubaronsendcommand"></a><a name="onsendcommand"></a>CMFCMenuBar::OnSendCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsetdefaultbuttontexta--cmfcmenubaronsetdefaultbuttontext"></a><a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText  
 フレームワークは、メニュー バーで、項目のテキストを変更したときに、このメソッドを呼び出します。  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ポインター、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)ユーザーがカスタマイズするオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームワークは、メニュー バーにユーザーの変更を適用する場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドの既定の実装は、ボタンのテキストをユーザーが指定したテキストに変更します。  
  
##  <a name="a-nameontoolhittesta--cmfcmenubarontoolhittest"></a><a name="ontoolhittest"></a>CMFCMenuBar::OnToolHitTest  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `pTI`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namepretranslatemessagea--cmfcmenubarpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namerestoreoriginalstatea--cmfcmenubarrestoreoriginalstate"></a><a name="restoreoriginalstate"></a>CMFCMenuBar::RestoreOriginalstate  
 ユーザーが選択したときに、フレームワークによって呼び出されます**リセット**から、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーを選択すると、このメソッドが呼び出されます**リセット**のカスタマイズ メニューからです。 また、手動でプログラムを使用して、メニュー バーの状態をリセットするには、このメソッドを呼び出すことができます。 このメソッドは、リソース ファイルから元の状態を読み込みます。  
  
 このメソッドをオーバーライドして、ユーザーが選択したすべての処理を実行する場合、**リセット**オプション。  
  
##  <a name="a-namesavestatea--cmfcmenubarsavestate"></a><a name="savestate"></a>CMFCMenuBar::SaveState  
 状態を保存、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Windows レジストリにオブジェクトです。  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 Windows レジストリ キーのパスを含む文字列です。  
  
 [入力] `nIndex`  
 メニュー バーのコントロールの ID。  
  
 [入力] `uiID`  
 予約済みの値。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 通常、アプリケーションは呼び出しません`SaveState`します。 フレームワークは、ワークスペースがシリアル化する場合に、このメソッドを呼び出します。 詳細については、次を参照してください。 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)します。  
  
 保存されている情報には、メニュー項目には、ドッキング状態では、メニュー バーの位置が含まれます。  
  
##  <a name="a-namesetdefaultmenuresida--cmfcmenubarsetdefaultmenuresid"></a><a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId  
 既定のメニューの設定、 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)オブジェクトに基づいて、リソース id。  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiResId`  
 新しい既定のメニューのリソース ID です。  
  
### <a name="remarks"></a>コメント  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)メソッドは、リソース ファイルから既定のメニューを復元します。  
  
 使用して、 [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)を使わずに既定のメニューを取得します。  
  
##  <a name="a-namesetforcedownarrowsa--cmfcmenubarsetforcedownarrows"></a><a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownArrows  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bValue`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetmaximizemodea--cmfcmenubarsetmaximizemode"></a><a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode  
 フレームワークは、MDI の表示モードを変更すると、メニュー バーを更新する必要が、このメソッドを呼び出します。  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMax`  
 モードを指定するブール値。 詳細については、次の「解説」を参照してください。  
  
 [入力] `pWnd`  
 変更されている MDI 子ウィンドウへのポインター。  
  
 [入力] `bRecalcLayout`  
 メニュー バーのレイアウトをすぐに計算する必要があるかどうかを指定するブール値。  
  
### <a name="remarks"></a>コメント  
 MDI メイン フレーム ウィンドウにアタッチされているメニュー バーがシステム メニューを表示する MDI 子ウィンドウが最大化されているときに、**最小化**、**最大化**と**閉じる**ボタン。 場合`bMax`は`TRUE`と`pWnd`は`NULL`MDI 子ウィンドウを最大化し、メニュー バーは、追加のコントロールを組み込む必要があります。 それ以外の場合、メニュー バーは、通常の状態に戻ります。  
  
##  <a name="a-namesetmenubuttonrtca--cmfcmenubarsetmenubuttonrtc"></a><a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC  
 ユーザーがメニュー ボタンを作成するときにフレームワークが使用するランタイム クラス情報を設定します。  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuButtonRTC`  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)から派生したクラスの情報、 [CMFCMenuButton クラス](../../mfc/reference/cmfcmenubutton-class.md)します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが新しいボタンをメニュー バーに追加すると、フレームワークは動的にボタンを作成します。 既定で作成`CMFCMenuButton`オブジェクトです。 フレームワークを作成する button オブジェクトの種類を変更するには、このメソッドをオーバーライドします。  
  
##  <a name="a-namesetmenufonta--cmfcmenubarsetmenufont"></a><a name="setmenufont"></a>CMFCMenuBar::SetMenuFont  
 アプリケーションのすべてのメニュー バーのフォントを設定します。  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpLogFont`  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327)を設定するフォントを定義する構造体。  
  
 [入力] `bHorz`  
 TRUE の場合は、`lpLogFont`縦書きフォント、FALSE 横書きフォントに使用する場合に使用するパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 すべての&2; つのフォントが使用される`CMFCMenuBar`オブジェクトです。 水平および垂直方向のメニュー バーでは、これら個別のフォントが使用されます。  
  
 フォント設定は、グローバル変数し、すべてに影響を与える`CMFCMenuBar`オブジェクトです。  
  
##  <a name="a-namesetrecentlyusedmenusa--cmfcmenubarsetrecentlyusedmenus"></a><a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus  
 メニュー コマンドを使用して、メニュー バーが最近表示されるかどうかを制御します。  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bOn`  
 最近使用したメニューのコマンドを表示するかどうかを制御するブール値。  
  
##  <a name="a-namesetshowallcommandsa--cmfcmenubarsetshowallcommands"></a><a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands  
 メニューが使用可能なすべてのコマンドを表示するかどうかを制御します。  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShowAllCommands`  
 ポップアップ メニューがメニュー コマンドのすべてを表示するかどうかを指定するブール値パラメーターです。  
  
### <a name="remarks"></a>コメント  
 メニューで、すべてのメニュー コマンドが表示されない場合は、あまり活用されていないコマンドが表示されません。 メニュー コマンドを表示する方法についての詳細については、次を参照してください。 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)

