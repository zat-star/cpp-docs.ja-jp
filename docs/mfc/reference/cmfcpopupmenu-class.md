---
title: "CMFCPopupMenu クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenu
- AFXPOPUPMENU/CMFCPopupMenu
- AFXPOPUPMENU/CMFCPopupMenu::CMFCPopupMenu
- AFXPOPUPMENU/CMFCPopupMenu::ActivatePopupMenu
- AFXPOPUPMENU/CMFCPopupMenu::AlwaysShowEmptyToolsEntry
- AFXPOPUPMENU/CMFCPopupMenu::AreAllCommandsShown
- AFXPOPUPMENU/CMFCPopupMenu::CheckArea
- AFXPOPUPMENU/CMFCPopupMenu::CloseMenu
- AFXPOPUPMENU/CMFCPopupMenu::Create
- AFXPOPUPMENU/CMFCPopupMenu::DefaultMouseClickOnClose
- AFXPOPUPMENU/CMFCPopupMenu::EnableMenuLogo
- AFXPOPUPMENU/CMFCPopupMenu::EnableMenuSound
- AFXPOPUPMENU/CMFCPopupMenu::EnableResize
- AFXPOPUPMENU/CMFCPopupMenu::EnableScrolling
- AFXPOPUPMENU/CMFCPopupMenu::EnableVertResize
- AFXPOPUPMENU/CMFCPopupMenu::FindSubItemByCommand
- AFXPOPUPMENU/CMFCPopupMenu::GetActiveMenu
- AFXPOPUPMENU/CMFCPopupMenu::GetAnimationSpeed
- AFXPOPUPMENU/CMFCPopupMenu::GetAnimationType
- AFXPOPUPMENU/CMFCPopupMenu::GetDropDirection
- AFXPOPUPMENU/CMFCPopupMenu::GetForceMenuFocus
- AFXPOPUPMENU/CMFCPopupMenu::GetForceShadow
- AFXPOPUPMENU/CMFCPopupMenu::GetHMenu
- AFXPOPUPMENU/CMFCPopupMenu::GetMenuBar
- AFXPOPUPMENU/CMFCPopupMenu::GetMenuItem
- AFXPOPUPMENU/CMFCPopupMenu::GetMenuItemCount
- AFXPOPUPMENU/CMFCPopupMenu::GetMessageWnd
- AFXPOPUPMENU/CMFCPopupMenu::GetParentArea
- AFXPOPUPMENU/CMFCPopupMenu::GetParentButton
- AFXPOPUPMENU/CMFCPopupMenu::GetParentPopupMenu
- AFXPOPUPMENU/CMFCPopupMenu::GetParentRibbonElement
- AFXPOPUPMENU/CMFCPopupMenu::GetParentToolBar
- AFXPOPUPMENU/CMFCPopupMenu::GetQuickCustomizeType
- AFXPOPUPMENU/CMFCPopupMenu::GetSelItem
- AFXPOPUPMENU/CMFCPopupMenu::HasBeenResized
- AFXPOPUPMENU/CMFCPopupMenu::HideRarelyUsedCommands
- AFXPOPUPMENU/CMFCPopupMenu::InCommand
- AFXPOPUPMENU/CMFCPopupMenu::InsertItem
- AFXPOPUPMENU/CMFCPopupMenu::InsertSeparator
- AFXPOPUPMENU/CMFCPopupMenu::IsAlwaysClose
- AFXPOPUPMENU/CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry
- AFXPOPUPMENU/CMFCPopupMenu::IsCustomizePane
- AFXPOPUPMENU/CMFCPopupMenu::IsEscClose
- AFXPOPUPMENU/CMFCPopupMenu::IsIdle
- AFXPOPUPMENU/CMFCPopupMenu::IsMenuSound
- AFXPOPUPMENU/CMFCPopupMenu::IsQuickCustomize
- AFXPOPUPMENU/CMFCPopupMenu::IsResizeble
- AFXPOPUPMENU/CMFCPopupMenu::IsRightAlign
- AFXPOPUPMENU/CMFCPopupMenu::IsScrollable
- AFXPOPUPMENU/CMFCPopupMenu::IsSendMenuSelectMsg
- AFXPOPUPMENU/CMFCPopupMenu::IsShown
- AFXPOPUPMENU/CMFCPopupMenu::MoveTo
- AFXPOPUPMENU/CMFCPopupMenu::OnCmdMsg
- AFXPOPUPMENU/CMFCPopupMenu::PostCommand
- AFXPOPUPMENU/CMFCPopupMenu::PreTranslateMessage
- AFXPOPUPMENU/CMFCPopupMenu::RecalcLayout
- AFXPOPUPMENU/CMFCPopupMenu::RemoveAllItems
- AFXPOPUPMENU/CMFCPopupMenu::RemoveItem
- AFXPOPUPMENU/CMFCPopupMenu::SaveState
- AFXPOPUPMENU/CMFCPopupMenu::SetAnimationSpeed
- AFXPOPUPMENU/CMFCPopupMenu::SetAnimationType
- AFXPOPUPMENU/CMFCPopupMenu::SetAutoDestroy
- AFXPOPUPMENU/CMFCPopupMenu::SetDefaultItem
- AFXPOPUPMENU/CMFCPopupMenu::SetForceMenuFocus
- AFXPOPUPMENU/CMFCPopupMenu::SetForceShadow
- AFXPOPUPMENU/CMFCPopupMenu::SetMaxWidth
- AFXPOPUPMENU/CMFCPopupMenu::SetMessageWnd
- AFXPOPUPMENU/CMFCPopupMenu::SetParentRibbonElement
- AFXPOPUPMENU/CMFCPopupMenu::SetQuickCustomizeType
- AFXPOPUPMENU/CMFCPopupMenu::SetQuickMode
- AFXPOPUPMENU/CMFCPopupMenu::SetRightAlign
- AFXPOPUPMENU/CMFCPopupMenu::SetSendMenuSelectMsg
- AFXPOPUPMENU/CMFCPopupMenu::ShowAllCommands
- AFXPOPUPMENU/CMFCPopupMenu::TriggerResize
- AFXPOPUPMENU/CMFCPopupMenu::UpdateAllShadows
- AFXPOPUPMENU/CMFCPopupMenu::UpdateShadow
- AFXPOPUPMENU/CMFCPopupMenu::CreateTearOffBar
- AFXPOPUPMENU/CMFCPopupMenu::OnChangeHot
- AFXPOPUPMENU/CMFCPopupMenu::OnChooseItem
dev_langs:
- C++
helpviewer_keywords:
- CMFCPopupMenu class
ms.assetid: 9555dca1-8c9c-44c9-af72-0659ddad128e
caps.latest.revision: 40
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a45f4e1b73c7cbff994c0b360c01c2f331ccab23
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpopupmenu-class"></a>CMFCPopupMenu クラス
Windows のポップアップ メニュー機能を実装し、ティアオフ メニューやツールヒントなどの機能を追加することでそれを拡張します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPopupMenu : public CMiniFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPopupMenu::CMFCPopupMenu](#cmfcpopupmenu)|`CMFCPopupMenu` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPopupMenu::ActivatePopupMenu](#activatepopupmenu)||  
|[CMFCPopupMenu::AlwaysShowEmptyToolsEntry](#alwaysshowemptytoolsentry)|ユーザー定義のツールの空のエントリを表示するポップアップ メニューが有効になっているかどうかを設定します。|  
|[CMFCPopupMenu::AreAllCommandsShown](#areallcommandsshown)||  
|[CMFCPopupMenu::CheckArea](#checkarea)|ポップアップ メニューの基準とした点の位置を決定します。|  
|[CMFCPopupMenu::CloseMenu](#closemenu)||  
|[CMFCPopupMenu::Create](#create)|ポップアップ メニューを作成し、それをアタッチ、`CMFCPopupMenu`オブジェクトです。|  
|[CMFCPopupMenu::DefaultMouseClickOnClose](#defaultmouseclickonclose)||  
|[CMFCPopupMenu::EnableMenuLogo](#enablemenulogo)|ポップアップ メニューのロゴを初期化します。|  
|[CMFCPopupMenu::EnableMenuSound](#enablemenusound)|メニューのサウンドを有効にします。|  
|[CMFCPopupMenu::EnableResize](#enableresize)||  
|[CMFCPopupMenu::EnableScrolling](#enablescrolling)||  
|[CMFCPopupMenu::EnableVertResize](#enablevertresize)||  
|[CMFCPopupMenu::FindSubItemByCommand](#findsubitembycommand)||  
|[CMFCPopupMenu::GetActiveMenu](#getactivemenu)|現在アクティブなメニューを返します。|  
|[CMFCPopupMenu::GetAnimationSpeed](#getanimationspeed)|ポップアップ メニューのアニメーションの速度を返します。|  
|[CMFCPopupMenu::GetAnimationType](#getanimationtype)|ポップアップ メニューのアニメーションの現在の型を返します。|  
|[CMFCPopupMenu::GetDropDirection](#getdropdirection)||  
|[CMFCPopupMenu::GetForceMenuFocus](#getforcemenufocus)|メニュー バー、ポップアップ メニューが表示されたときに、フォーカスを返すかどうかを示します。|  
|[CMFCPopupMenu::GetForceShadow](#getforceshadow)||  
|[CMFCPopupMenu::GetHMenu](#gethmenu)|関連付けられたメニュー リソースへのハンドルを返します。|  
|[CMFCPopupMenu::GetMenuBar](#getmenubar)|返します。、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 、ポップアップ メニュー内に埋め込まれています。|  
|[CMFCPopupMenu::GetMenuItem](#getmenuitem)|指定したインデックスにあるメニュー項目へのポインターを返します。|  
|[CMFCPopupMenu::GetMenuItemCount](#getmenuitemcount)|ポップアップ メニュー項目の数を返します。|  
|[CMFCPopupMenu::GetMessageWnd](#getmessagewnd)|ポップアップ メニュー メッセージのルーティング先ウィンドウへのポインターを返します。|  
|[CMFCPopupMenu::GetParentArea](#getparentarea)||  
|[CMFCPopupMenu::GetParentButton](#getparentbutton)|親ツールバー ボタンへのポインターを返します。|  
|[CMFCPopupMenu::GetParentPopupMenu](#getparentpopupmenu)|親のポップアップ メニューへのポインターを返します。|  
|[CMFCPopupMenu::GetParentRibbonElement](#getparentribbonelement)||  
|[CMFCPopupMenu::GetParentToolBar](#getparenttoolbar)|親ツールバーへのポインターを返します。|  
|[CMFCPopupMenu::GetQuickCustomizeType](#getquickcustomizetype)||  
|[CMFCPopupMenu::GetSelItem](#getselitem)|現在選択されているメニュー コマンドへのポインターを返します。|  
|[CMFCPopupMenu::HasBeenResized](#hasbeenresized)||  
|[CMFCPopupMenu::HideRarelyUsedCommands](#hiderarelyusedcommands)|ポップアップ メニューがあまり使用されないコマンドを非表示にするかどうかを示します。|  
|[CMFCPopupMenu::InCommand](#incommand)||  
|[CMFCPopupMenu::InsertItem](#insertitem)|指定した場所に、ポップアップ メニューに新しい項目を挿入します。|  
|[CMFCPopupMenu::InsertSeparator](#insertseparator)|指定した場所に、ポップアップ メニューに、区切り記号を挿入します。|  
|[CMFCPopupMenu::IsAlwaysClose](#isalwaysclose)||  
|[CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry](#isalwaysshowemptytoolsentry)||  
|[CMFCPopupMenu::IsCustomizePane](#iscustomizepane)|ポップアップ メニューが機能しているかどうかを示す、 **QuickCustomizePane**します。|  
|[CMFCPopupMenu::IsEscClose](#isescclose)||  
|[CMFCPopupMenu::IsIdle](#isidle)|ポップアップ メニューが現在休止状態かどうかを示します。|  
|[CMFCPopupMenu::IsMenuSound](#ismenusound)||  
|[CMFCPopupMenu::IsQuickCustomize](#isquickcustomize)|決定かどうか、関連付けられている[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)QuickCustomize モードにします。|  
|[CMFCPopupMenu::IsResizeble](#isresizeble)||  
|[CMFCPopupMenu::IsRightAlign](#isrightalign)|メニューが右揃えまたは左揃えするかどうかを示します。|  
|[CMFCPopupMenu::IsScrollable](#isscrollable)||  
|[CMFCPopupMenu::IsSendMenuSelectMsg](#issendmenuselectmsg)|フレームワークが、ユーザー、ポップアップ メニューからコマンドを選択したときに、親フレームを通知するかどうかを示します。|  
|[CMFCPopupMenu::IsShown](#isshown)|ポップアップ メニューが表示されているかどうかを示します。|  
|[CMFCPopupMenu::MoveTo](#moveto)||  
|[CMFCPopupMenu::OnCmdMsg](#oncmdmsg)|( `CFrameWnd::OnCmdMsg`をオーバーライドします)。|  
|[CMFCPopupMenu::PostCommand](#postcommand)||  
|[CMFCPopupMenu::PreTranslateMessage](#pretranslatemessage)|(`CFrameWnd::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCPopupMenu::RecalcLayout](#recalclayout)|オンまたはオフに標準のコントロール バーが切り替えられたときに、またはフレーム ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。 (上書き[表示](../../mfc/reference/cframewnd-class.md#recalclayout))。|  
|[CMFCPopupMenu::RemoveAllItems](#removeallitems)|ポップアップ メニューからのすべての項目をクリアします。|  
|[CMFCPopupMenu::RemoveItem](#removeitem)|ポップアップ メニューから、指定した項目を削除します。|  
|[CMFCPopupMenu::SaveState](#savestate)||  
|[CMFCPopupMenu::SetAnimationSpeed](#setanimationspeed)|ポップアップ メニューのアニメーションの速度を設定します。|  
|[CMFCPopupMenu::SetAnimationType](#setanimationtype)|ポップアップ メニューのアニメーションの種類を設定します。|  
|[CMFCPopupMenu::SetAutoDestroy](#setautodestroy)||  
|[CMFCPopupMenu::SetDefaultItem](#setdefaultitem)|ポップアップ メニューの既定のコマンドを設定します。|  
|[CMFCPopupMenu::SetForceMenuFocus](#setforcemenufocus)|メニュー バー、ポップアップ メニューが表示される場合に返される入力フォーカスを強制します。|  
|[CMFCPopupMenu::SetForceShadow](#setforceshadow)|ポップアップ メニューがメイン フレームの外側に表示時にメニュー シャドウを描画するために、フレームワークを強制します。|  
|[CMFCPopupMenu::SetMaxWidth](#setmaxwidth)|ポップアップ メニューの最大幅を設定します。|  
|[CMFCPopupMenu::SetMessageWnd](#setmessagewnd)||  
|[CMFCPopupMenu::SetParentRibbonElement](#setparentribbonelement)||  
|[CMFCPopupMenu::SetQuickCustomizeType](#setquickcustomizetype)||  
|[CMFCPopupMenu::SetQuickMode](#setquickmode)||  
|[CMFCPopupMenu::SetRightAlign](#setrightalign)|ポップアップ メニューのメニューの配置を設定します。|  
|[CMFCPopupMenu::SetSendMenuSelectMsg](#setsendmenuselectmsg)|コマンドを選択すると、ポップアップ メニューが親フレームを通知するかどうかを制御するフラグを設定します。|  
|[CMFCPopupMenu::ShowAllCommands](#showallcommands)|すべてのコマンドを表示するポップアップ メニューを強制します。|  
|[CMFCPopupMenu::TriggerResize](#triggerresize)||  
|[CMFCPopupMenu::UpdateAllShadows](#updateallshadows)|すべての開かれたポップアップ メニューの影を更新します。|  
|[CMFCPopupMenu::UpdateShadow](#updateshadow)|ポップアップ メニューの影を更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPopupMenu::CreateTearOffBar](#createtearoffbar)||  
|[CMFCPopupMenu::OnChangeHot](#onchangehot)||  
|[CMFCPopupMenu::OnChooseItem](#onchooseitem)||  
  
### <a name="remarks"></a>コメント  
 通常、MFC はポップアップ メニューを自動的に作成します。 作成する場合、`CMFCPopupMenu`手動でのオブジェクト、1 つは、ヒープの割り当てし、呼び出す[CMFCPopupMenu::Create](#create)します。  
  
## <a name="example"></a>例  
 次の例では、ポップアップ メニュー オブジェクトを構成する方法を示します。 この例では、ロゴと、ポップアップ メニューのサウンド設定、アニメーションの速度と種類を設定、メニュー シャドウを描画、ポップアップ メニューがメイン フレーム以外の場所が表示されたら、最大の幅を設定し、ポップアップ メニューの右側のメニューの配置を設定する方法を示します。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages&#2;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenu-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 `CMFCPopupMenu`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpopupmenu.h  
  
##  <a name="activatepopupmenu"></a>CMFCPopupMenu::ActivatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall ActivatePopupMenu(
    CFrameWnd* pTopFrame,  
    CMFCPopupMenu* pPopupMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTopFrame`  
 [入力] `pPopupMenu`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="alwaysshowemptytoolsentry"></a>CMFCPopupMenu::AlwaysShowEmptyToolsEntry  
 ユーザー定義のツールの空のエントリを表示するポップアップ メニューが有効になっているかどうかを設定します。  
  
```  
static void AlwaysShowEmptyToolsEntry(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE`ポップアップ メニューが空のエントリを表示できる場合`FALSE`それ以外の場合。  
  
##  <a name="areallcommandsshown"></a>CMFCPopupMenu::AreAllCommandsShown  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AreAllCommandsShown() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkarea"></a>CMFCPopupMenu::CheckArea  
 ポップアップ メニューの基準とした点の位置を決定します。  
  
```  
MENUAREA_TYPE CheckArea(const CPoint& ptScreen) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ptScreen`  
 画面座標にポイントします。  
  
### <a name="return-value"></a>戻り値  
 そのポイントが、ポップアップ メニューに対して相対的であることを示す MENUAREA_TYPE パラメーター。  
  
### <a name="remarks"></a>コメント  
 MENUAREA_TYPE パラメーターには、次の値のいずれかのことができます。  
  
-   外部の`ptScreen`が、ポップアップ メニューの範囲外です。  
  
-   ロゴ -`ptScreen`がロゴ領域を超えています。  
  
-   TEAROFF_CAPTION -`ptScreen`がティアオフ キャプションを超えています。  
  
-   SHADOW_BOTTOM -`ptScreen`がポップアップ メニューの下部にあるシャドウを超えています。  
  
-   SHADOW_RIGHT -`ptScreen`が、ポップアップ メニューの適切影を超えています。  
  
-   メニュー -`ptScreen`がコマンドを超えています。  
  
##  <a name="closemenu"></a>CMFCPopupMenu::CloseMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void CloseMenu(BOOL bSetFocusToBar = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSetFocusToBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcpopupmenu"></a>CMFCPopupMenu::CMFCPopupMenu  
 構築、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトです。  
  
```  
CMFCPopupMenu(
    CMFCToolBarsMenuPropertyPage* pCustPage,  
    LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCustPage`  
 カスタマイズ ページへのポインター。  
  
 [入力] `lpszTitle`  
 メニュー キャプションを表す文字列。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、のリソースを割り当て、`CMFCPopupMenu`です。 ポップアップ メニュー項目を作成するには[CMFCPopupMenu::Create](#create)します。  
  
##  <a name="create"></a>CMFCPopupMenu::Create  
 ポップアップ メニューを作成し、それをアタッチ、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    HMENU hMenu,  
    BOOL bLocked = FALSE,  
    BOOL bOwnMessage = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウ、`CMFCPopupMenu`です。  
  
 [入力] `x`  
 ポップアップ メニューの場所の水平画面座標  
  
 [入力] `y`  
 ポップアップ メニューの場所の垂直画面座標。  
  
 [入力] `hMenu`  
 メニュー リソースへのハンドル。  
  
 [入力] `bLocked`  
 メニューは、カスタマイズ可能かどうかを示すブール値パラメーターです。 `FALSE`ポップアップ メニューがカスタマイズ可能なことを示します。  
  
 [入力] `bOwnMessage`  
 メニューの メッセージのルーティング方法を示すブール値パラメーターです。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 場合`bOwnMessage`は`TRUE`、すべてのメニュー メッセージのルーティング`pWndParent`します。 `pWndParent`ことはできません`NULL`場合`bOwnMessage`は`TRUE.`場合`bOwnMessage`は`FALSE`フレームワークでは、親のポップアップ メニューにメニュー メッセージをルーティングします。  
  
### <a name="example"></a>例  
 次の例では、使用して、`Create`のメソッド、`CMFCPopuMenu`クラスです。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages&#1;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenu-class_2.cpp)]  
  
##  <a name="createtearoffbar"></a>CMFCPopupMenu::CreateTearOffBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndMain`  
 [入力] `uiID`  
 [入力] `lpszName`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="defaultmouseclickonclose"></a>CMFCPopupMenu::DefaultMouseClickOnClose  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DefaultMouseClickOnClose() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablemenulogo"></a>CMFCPopupMenu::EnableMenuLogo  
 ポップアップ メニューのロゴを初期化します。  
  
```  
void EnableMenuLogo(
    int iLogoSize,  
    LOGO_LOCATION nLogoLocation = MENU_LOGO_LEFT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iLogoSize`  
 (ピクセル単位)、ロゴのサイズ。  
  
 [入力] `nLogoLocation`  
 ロゴの位置を示す列挙型。  
  
### <a name="remarks"></a>コメント  
 ロゴを表示するメソッドを実装する[CFrameWndEx::OnDrawMenuLogo](../../mfc/reference/cframewndex-class.md#ondrawmenulogo)メイン フレーム ウィンドウにします。  
  
 ような値`nLogoLocation`は MENU_LOGO_LEFT、MENU_LOGO_RIGHT、MENU_LOGO_TOP、および MENU_LOGO_BOTTOM です。  
  
##  <a name="enablemenusound"></a>CMFCPopupMenu::EnableMenuSound  
 メニューのサウンドを有効にします。  
  
```  
static void EnableMenuSound(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`サウンドを有効にする`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 サウンドを有効にした場合、フレームワーク、 [PlaySound](http://msdn.microsoft.com/library/windows/desktop/bb774426)メソッドと、ユーザーがポップアップ メニューを開くか、メニュー コマンドを選択します。 既定では、この機能が有効にします。  
  
##  <a name="enableresize"></a>CMFCPopupMenu::EnableResize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableResize(CSize sizeMinResize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `sizeMinResize`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablescrolling"></a>CMFCPopupMenu::EnableScrolling  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableScrolling(BOOL = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `BOOL`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablevertresize"></a>CMFCPopupMenu::EnableVertResize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableVertResize(int nMinResize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMinResize`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findsubitembycommand"></a>CMFCPopupMenu::FindSubItemByCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolBarMenuButton* FindSubItemByCommand(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getactivemenu"></a>CMFCPopupMenu::GetActiveMenu  
 現在アクティブなメニューを返します。  
  
```  
static CMFCPopupMenu* GetActiveMenu();
```  
  
### <a name="return-value"></a>戻り値  
 作業中のポップアップ メニューまたはポップアップ メニューが現在アクティブになっていない場合は NULL へのポインター。  
  
### <a name="remarks"></a>コメント  
 各アプリケーションには、最大で&1; つアクティブなポップアップ メニューをことができます。  
  
##  <a name="getanimationspeed"></a>CMFCPopupMenu::GetAnimationSpeed  
 ポップアップ メニューのアニメーションの速度を返します。  
  
```  
static UINT GetAnimationSpeed();
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューのアニメーションが終了するまでをミリ秒単位での時間を示す整数。  
  
### <a name="remarks"></a>コメント  
 アニメーションの速度は、グローバル値です。 使用[CMFCPopupMenu::SetAnimationSpeed](#setanimationspeed)ポップアップ メニューのアニメーションの速度を変更します。  
  
##  <a name="getanimationtype"></a>CMFCPopupMenu::GetAnimationType  
 ポップアップ アニメーションの現在の型を返します。  
  
```  
static CMFCPopupMenu::ANIMATION_TYPE GetAnimationType(BOOL bNoSystem = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNoSystem`  
 このメソッドをグローバル値をチェックするかどうかを示すブール値パラメーターです。 このメソッドのこのインスタンスのアニメーションのスタイルを取得する場合は FALSE、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 アニメーションの種類を示す列挙値。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューのアニメーションのスタイルは、アプリケーションに対してグローバルです。 使用[CMFCPopupMenu::SetAnimationType](#setanimationtype)アニメーションのスタイルを設定します。  
  
 次の表は、可能なアニメーションの種類を一覧表示します。  
  
 NO_ANIMATION  
 ポップアップ メニューでは、アニメーション化されていないと、すぐに表示されます。  
  
 展開  
 フレームワークでは、左上隅から右下隅のポップアップ メニューが表示されます。  
  
 スライド  
 ポップアップ メニューは、上から下へ移動します。  
  
 フェード  
 ポップアップ メニューでは、まず透明のように表示され、徐々 に塗りつぶされます。  
  
##  <a name="getdropdirection"></a>CMFCPopupMenu::GetDropDirection  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
DROP_DIRECTION GetDropDirection() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getforcemenufocus"></a>CMFCPopupMenu::GetForceMenuFocus  
 メニュー バー、ポップアップ メニューが表示されたときに、フォーカスを返すかどうかを示します。  
  
```  
static BOOL GetForceMenuFocus();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューが表示されます。 ときに、メニュー バーに入力フォーカスが返される場合`FALSE`場合は、ポップアップ メニューがフォーカスを保持します。  
  
### <a name="remarks"></a>コメント  
 既定では、アプリケーションは、メニュー バーにフォーカスを返しません。 この設定を変更するには使用[CMFCPopupMenu::SetForceMenuFocus](#setforcemenufocus)します。  
  
##  <a name="getforceshadow"></a>CMFCPopupMenu::GetForceShadow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall GetForceShadow();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gethmenu"></a>CMFCPopupMenu::GetHMenu  
 関連付けられたメニュー リソースへのハンドルを返します。  
  
```  
HMENU GetHMenu();
```  
  
##  <a name="getmenubar"></a>CMFCPopupMenu::GetMenuBar  
 返します。、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 、ポップアップ メニュー内に埋め込まれています。  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>戻り値  
 埋め込まれたへのポインター`CMFCPopupMenuBar`します。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューが、埋め込み`CMFCPopupMenuBar`オブジェクトです。 別の埋め込みクラスを使用している場合は、派生クラスでは、このメソッドをオーバーライドする必要があります。  
  
##  <a name="getmenuitem"></a>CMFCPopupMenu::GetMenuItem  
 指定したインデックスにあるメニュー項目へのポインターを返します。  
  
```  
CMFCToolBarMenuButton* GetMenuItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 メニュー項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 メニュー項目へのポインター。 `NULL`インデックスが無効な場合です。  
  
### <a name="remarks"></a>コメント  
 メニュー項目がによって表される、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)します。 適切なポインターを返すこのメソッドを呼び出すと、`CMFCToolBarMenuButton`です。  
  
##  <a name="getmenuitemcount"></a>CMFCPopupMenu::GetMenuItemCount  
 ポップアップ メニューの項目の数を返します。  
  
```  
int GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー項目の数。  
  
##  <a name="getmessagewnd"></a>CMFCPopupMenu::GetMessageWnd  
 ポップアップ メニュー メッセージのルーティング先ウィンドウへのポインターを返します。  
  
```  
CWnd* GetMessageWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューのメッセージを受信するウィンドウへのポインター`NULL`ウィンドウがない場合。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用すると[CMFCPopupMenu::Create](#create)ポップアップ メニューを作成するには、指定したどのようなウィンドウ] メニューの [メッセージを受け取ります。  
  
##  <a name="getparentarea"></a>CMFCPopupMenu::GetParentArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetParentArea(CRect& rectParentBtn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectParentBtn`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getparentbutton"></a>CMFCPopupMenu::GetParentButton  
 親ツールバー ボタンへのポインターを返します。  
  
```  
CMFCToolBarMenuButton* GetParentButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ツールバー ボタンへのポインター。 `NULL`場合は、ポップアップ メニューには、親のツール バー ボタンは与えません。  
  
### <a name="remarks"></a>コメント  
 A`CMFCPopupMenu`メニューのボタンを関連付けることができます。 このシナリオでは、ユーザーが親のツール バー ボタンを選択したときに、ポップアップ メニューが表示されます。  
  
 ポップアップ メニューにショートカット メニューがある場合はありません親ツールバー ボタンをクリックします。  
  
##  <a name="getparentpopupmenu"></a>CMFCPopupMenu::GetParentPopupMenu  
 親のポップアップ メニューへのポインターを返します。  
  
```  
CMFCPopupMenu* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親へのポインター`CMFCPopupMenu`オブジェクトです。`NULL`親ポップアップ メニューがない場合。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューが親を持つ`CMFCPopupMenu`オブジェクト、サブメニューであるかどうかのみです。  
  
##  <a name="getparentribbonelement"></a>CMFCPopupMenu::GetParentRibbonElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentRibbonElement() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getparenttoolbar"></a>CMFCPopupMenu::GetParentToolBar  
 親ツールバーへのポインターを返します。  
  
```  
CMFCToolBar* GetParentToolBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ツールバーへのポインター。 `NULL`親ツールバー、ポップアップ メニューがない場合。  
  
### <a name="remarks"></a>コメント  
 場合、`CMFCPopupMenu`がショートカット メニュー、ツールバーの親を持たない。  
  
##  <a name="getquickcustomizetype"></a>CMFCPopupMenu::GetQuickCustomizeType  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
QUICK_CUSTOMIZE_TYPE GetQuickCustomizeType() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getselitem"></a>CMFCPopupMenu::GetSelItem  
 現在選択されているメニュー コマンドへのポインターを返します。  
  
```  
CMFCToolBarMenuButton* GetSelItem();
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているメニューへのポインター`NULL`項目が選択されていない場合。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューにメニュー コマンドは、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)から派生するクラスまたは`CMFCToolBarMenuButton`です。  
  
##  <a name="hasbeenresized"></a>CMFCPopupMenu::HasBeenResized  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL HasBeenResized() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hiderarelyusedcommands"></a>CMFCPopupMenu::HideRarelyUsedCommands  
 ポップアップ メニューがあまり使用されないコマンドを非表示にするかどうかを示します。  
  
```  
BOOL HideRarelyUsedCommands() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューには、あまり使用されないコマンドが非表示にする場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、その構成が有効になっているのであればほとんどのコマンドを使用ポップアップ メニューが非表示にするかどうかのみを指定します。 親ボタンがあり、親ウィンドウがから派生した場合、ポップアップ メニューがあまり使用されないコマンドを非表示ことができます、 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)します。 使用[CMFCMenuBar::SetRecentlyUsedMenus](../../mfc/reference/cmfcmenubar-class.md#setrecentlyusedmenus)この機能を有効にし、 [CMFCMenuBar::IsRecentlyUsedMenus](../../mfc/reference/cmfcmenubar-class.md#isrecentlyusedmenus)をこの機能が現在有効になっているかどうかを判断します。 親ウィンドウには、これら両方のメソッドを呼び出す必要があります。  
  
##  <a name="incommand"></a>CMFCPopupMenu::InCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL InCommand();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="insertitem"></a>CMFCPopupMenu::InsertItem  
 指定した場所に、ポップアップ メニューに新しい項目を挿入します。  
  
```  
int InsertItem(
    const CMFCToolBarMenuButton& button,  
    int iInsertA = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `button`  
 追加するメニュー項目への参照。  
  
 [入力] `iInsertAt`  
 新しい項目の&0; から始まるインデックス。 場合`iInsertAt`-1 で、項目がメニューの末尾に追加します。  
  
### <a name="return-value"></a>戻り値  
 項目が挿入された位置の&0; から始まるインデックス。 メソッドが失敗した場合は-1。  
  
### <a name="remarks"></a>コメント  
 無効な値を指定する場合、このメソッドは失敗`iInsertAt`、現在、ポップアップ メニューにあるアイテムの数よりも大きい整数などです。  
  
##  <a name="insertseparator"></a>CMFCPopupMenu::InsertSeparator  
 指定した場所に、ポップアップ メニューに、区切り記号を挿入します。  
  
```  
int InsertSeparator(int iInsertAt = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iInsertAt`  
 このメソッドで、区切り記号を挿入する位置の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 区切り記号が挿入された位置の&0; から始まるインデックス。 このメソッドが失敗した場合は-1。  
  
### <a name="remarks"></a>コメント  
 値の-1`iInsertAt`のため、このメソッドは、ポップアップ メニューの末尾に区切り記号を追加します。  
  
 このメソッドは失敗`iInsertAt`は値が無効です。  
  
##  <a name="isalwaysclose"></a>CMFCPopupMenu::IsAlwaysClose  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysClose() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isalwaysshowemptytoolsentry"></a>CMFCPopupMenu::IsAlwaysShowEmptyToolsEntry  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall IsAlwaysShowEmptyToolsEntry();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="iscustomizepane"></a>CMFCPopupMenu::IsCustomizePane  
 ポップアップ メニューが機能しているかどうかを示す、 **QuickCustomizePane**します。  
  
```  
BOOL IsCustomizePane();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ ウィンドウがある場合、 **QuckCustomizePane**。 そうしないと`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 **QuickCustomizePane**を直接、ポップアップ メニューをカスタマイズするユーザーを有効にします。 **QuickCustomizePane**は、`CMFCPopupMenu`ユーザーが直接編集ツールバーのボタンをクリックしたときに表示されます。  
  
 アプリケーションが中にこのメソッドを呼び出す必要があります[CMDIFrameWndEx::OnShowCustomizePane](../../mfc/reference/cmdiframewndex-class.md#onshowcustomizepane)します。  
  
##  <a name="isescclose"></a>CMFCPopupMenu::IsEscClose  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsEscClose();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isidle"></a>CMFCPopupMenu::IsIdle  
 ポップアップ メニューが現在休止状態かどうかを示します。  
  
```  
virtual BOOL IsIdle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューがアイドル モードである場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 既定では、ポップアップ メニューがアイドル モード表示アニメーションが完了し、ユーザーが、ポップアップ メニューをスクロールしていない場合。  
  
##  <a name="ismenusound"></a>CMFCPopupMenu::IsMenuSound  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static UINT __stdcall IsMenuSound();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isquickcustomize"></a>CMFCPopupMenu::IsQuickCustomize  
 決定かどうか、関連付けられている[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)QuickCustomize モードにします。  
  
```  
BOOL IsQuickCustomize();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`関連するメニュー ボタンが QuickCustomize モードである場合それ以外の場合`FALSE`します。 このメソッドが返すことも`FALSE`、ポップアップ メニューが関連付けられていない場合、`CMFCToolBarMenuButton`です。  
  
### <a name="remarks"></a>コメント  
 QuickCustomize では、モード、ユーザーは、直接、ボタンをカスタマイズするツールバーのボタンを選択します。  
  
##  <a name="isresizeble"></a>CMFCPopupMenu::IsResizeble  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResizeble() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrightalign"></a>CMFCPopupMenu::IsRightAlign  
 メニューが右揃えまたは左揃えするかどうかを示します。  
  
```  
BOOL IsRightAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューが右揃えの場合`FALSE`場合は、メニューの左側に配置します。  
  
### <a name="remarks"></a>コメント  
 使用する[CMFCPopupMenu::SetRightAlign](#setrightalign)  メニューの配置を設定します。 既定では、ポップアップ メニューは、左揃えを使用します。  
  
 メニューの配置では、グローバル設定ではありませんし、ポップアップ メニューの間で異なることができます。  
  
##  <a name="isscrollable"></a>CMFCPopupMenu::IsScrollable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsScrollable() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="issendmenuselectmsg"></a>CMFCPopupMenu::IsSendMenuSelectMsg  
 フレームワークが、ユーザー、ポップアップ メニューからコマンドを選択したときに、親フレームを通知するかどうかを示します。  
  
```  
static BOOL IsSendMenuSelectMsg();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームワークが親フレームを通知する場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークに送信して親フレームを通知する、`WM_MENUSELECT`メッセージが表示されるメニュー コマンドを選択するために使用します。  
  
##  <a name="isshown"></a>CMFCPopupMenu::IsShown  
 ポップアップ メニューが表示されているかどうかを示します。  
  
```  
BOOL IsShown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ポップアップ メニューを表示する場合それ以外の場合`FALSE`します。  
  
##  <a name="moveto"></a>CMFCPopupMenu::MoveTo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void MoveTo(const CPoint& pt);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pt`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onchangehot"></a>CMFCPopupMenu::OnChangeHot  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChangeHot(int nHot);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHot`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onchooseitem"></a>CMFCPopupMenu::OnChooseItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChooseItem(UINT uidCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uidCmdID`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncmdmsg"></a>CMFCPopupMenu::OnCmdMsg  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 [入力] `nCode`  
 [入力] `pExtra`  
 [入力] `pHandlerInfo`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="postcommand"></a>CMFCPopupMenu::PostCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL PostCommand(UINT uiCommandID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCommandID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="pretranslatemessage"></a>CMFCPopupMenu::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="recalclayout"></a>CMFCPopupMenu::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeallitems"></a>CMFCPopupMenu::RemoveAllItems  
 ポップアップ メニューからのすべての項目をクリアします。  
  
```  
void RemoveAllItems();
```  
  
##  <a name="removeitem"></a>CMFCPopupMenu::RemoveItem  
 ポップアップ メニューから、指定した項目を削除します。  
  
```  
BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 削除する項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、項目の削除の影響を受けるすべての区切り記号を自動的に配置します。 フレームワークが区切り記号を再配置する方法の詳細については、次を参照してください。 [CMFCToolBar::RemoveButton](../../mfc/reference/cmfctoolbar-class.md#removebutton)します。  
  
##  <a name="savestate"></a>CMFCPopupMenu::SaveState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SaveState();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setanimationspeed"></a>CMFCPopupMenu::SetAnimationSpeed  
 ポップアップ メニューのアニメーションの速度を設定します。  
  
```  
static void SetAnimationSpeed(UINT nElapse);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nElapse`  
 新しいアニメーションの速度 (ミリ秒単位)。  
  
### <a name="remarks"></a>コメント  
 アニメーションの速度はグローバル値であり、アプリケーション内のすべてのポップアップ メニューに影響します。 この値は、[完了] ポップアップ メニューのアニメーションがかかる時間を指定します。  
  
 既定では、このパラメーターは 30 ミリ秒に設定されます。 有効な値の範囲`nElapse`は 0 ~ 200 です。  
  
##  <a name="setanimationtype"></a>CMFCPopupMenu::SetAnimationType  
 このポップアップ メニューのアニメーションの種類を設定します。  
  
```  
static void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `type`  
 アニメーションの種類を指定する列挙型。  
  
### <a name="remarks"></a>コメント  
 参照してください[CMFCPopupMenu::GetAnimationType](#getanimationtype)の有効な値の一覧については`type`です。  
  
##  <a name="setautodestroy"></a>CMFCPopupMenu::SetAutoDestroy  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAutoDestroy`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdefaultitem"></a>CMFCPopupMenu::SetDefaultItem  
 ポップアップ メニューの既定のコマンドを設定します。  
  
```  
void SetDefaultItem(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 新しい既定のコマンドのメニュー コマンド ID。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューで、既定のコマンドは、ポップアップ メニューが表示されるときに選択されるコマンドです。  
  
##  <a name="setforcemenufocus"></a>CMFCPopupMenu::SetForceMenuFocus  
 メニュー バー、ポップアップ メニューが表示される場合に返される入力フォーカスを強制します。  
  
```  
static void SetForceMenuFocus(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bValue`  
 `TRUE`ポップアップ メニューのメニュー バーに入力フォーカスを設定するフレームワークが必要な場合が表示されます。 `FALSE`ポップアップ メニューがフォーカスを保持する場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アプリケーション内のすべてのポップアップ メニューに対してグローバルに適用されるフラグを設定します。 既定では、この機能は無効です。  
  
##  <a name="setforceshadow"></a>CMFCPopupMenu::SetForceShadow  
 ポップアップ メニューがメイン フレームの外側に表示時にメニュー シャドウを描画するために、フレームワークを強制します。  
  
```  
static void SetForceShadow(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bValue`  
 `TRUE`メニュー シャドウを描画するためにフレームワークが必要な場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すときに、アプリケーションのグローバル フラグを設定します。 このフラグは、アプリケーション内のすべてのポップアップ メニューに影響します。  
  
##  <a name="setmaxwidth"></a>CMFCPopupMenu::SetMaxWidth  
 ポップアップ メニューの最大幅を設定します。  
  
```  
void SetMaxWidth(int iMaxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iMaxWidth`  
 ピクセル単位で、ポップアップ メニューの最大幅。  
  
### <a name="remarks"></a>コメント  
 メニュー コマンドに関連付けられたテキストは、最大の幅に収まらないは切り捨てられに一致しない部分は&3; つのドットで置き換えられます。  
  
##  <a name="setmessagewnd"></a>CMFCPopupMenu::SetMessageWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMessageWnd(CWnd* pMsgWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsgWnd`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setparentribbonelement"></a>CMFCPopupMenu::SetParentRibbonElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetParentRibbonElement(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pElem`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setquickcustomizetype"></a>CMFCPopupMenu::SetQuickCustomizeType  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetQuickCustomizeType(QUICK_CUSTOMIZE_TYPE Type);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Type`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setquickmode"></a>CMFCPopupMenu::SetQuickMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetQuickMode();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setrightalign"></a>CMFCPopupMenu::SetRightAlign  
 ポップアップ メニューのメニューの配置を設定します。  
  
```  
void SetRightAlign(BOOL bRightAlign = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bRightAlign`  
 メニューの配置を示すブール値。 `TRUE`右揃えを示す`FALSE`左揃えを示します。  
  
### <a name="remarks"></a>コメント  
 既定では、すべてのポップアップ メニューが左寄せします。  
  
##  <a name="setsendmenuselectmsg"></a>CMFCPopupMenu::SetSendMenuSelectMsg  
 コマンドを選択すると、ポップアップ メニューが親フレームを通知するかどうかを制御するフラグを設定します。  
  
```  
static void SetSendMenuSelectMsg(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE`ポップアップ メニューがその親のフレームに通知する場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 これは、アプリケーション内のすべてのポップアップ メニューのグローバルなオプションです。 ポップアップ メニューが送信が有効になっている場合、`WM_MENUSELECT`コマンドを選択すると親フレームへのメッセージ。  
  
##  <a name="showallcommands"></a>CMFCPopupMenu::ShowAllCommands  
 すべてのコマンドを表示するポップアップ メニューを強制します。  
  
```  
void ShowAllCommands();
```  
  
### <a name="remarks"></a>コメント  
 これにより、グローバル設定ではありませんし、現在のポップアップ メニューのみに影響します。  
  
##  <a name="triggerresize"></a>CMFCPopupMenu::TriggerResize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void TriggerResize();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="updateallshadows"></a>CMFCPopupMenu::UpdateAllShadows  
 すべての開かれたポップアップ メニューの影を更新します。  
  
```  
static void UpdateAllShadows(LPRECT lprectScreen = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lprectScreen`  
 画面座標で更新するには地域を指定する四角形。  
  
### <a name="remarks"></a>コメント  
 アニメーション コントロールまたは動的コンテンツを含む他のウィンドウをポップアップ メニューが表示されるときに、このメソッドの使用をお勧めします。  
  
##  <a name="updateshadow"></a>CMFCPopupMenu::UpdateShadow  
 ポップアップ メニューの影を更新します。  
  
```  
void UpdateShadow(LPRECT lprectScreen = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lprectScreen`  
 四角形を画面座標で更新する領域の境界を指定します。  
  
### <a name="remarks"></a>コメント  
 シャドウを含むポップアップ メニューがアニメーション画像と重なると、このメソッドを呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)

