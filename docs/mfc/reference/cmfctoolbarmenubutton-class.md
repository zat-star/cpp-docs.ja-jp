---
title: "CMFCToolBarMenuButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CompareWith
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CopyFrom
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateFromMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::EnableQuickCustomize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetCommands
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetImageRect
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPaletteRows
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HasButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HaveHotBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsClickedOnMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsDroppedDown
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsEmptyMenuAllowed
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsExclusive
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsQuickMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsTearOffMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnAfterCreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnBeforeDrag
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCalculateSize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCancelMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnChangeParentWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClick
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClickMenuItem
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnContextHelp
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDraw
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDrawOnCustomizeList
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OpenPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::ResetImageToDefault
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SaveBarState
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::Serialize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetACCData
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuOnly
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMessageWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetRadio
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetTearOff
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::DrawDocumentIcon
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarMenuButton class
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
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
ms.openlocfilehash: a06fd323862c6869463b4db0977816b5707c3e18
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarmenubutton-class"></a>CMFCToolBarMenuButton クラス
ポップアップ メニューを含むツール バー ボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](#cmfctoolbarmenubutton)|`CMFCToolBarMenuButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](#comparewith)|このインスタンスと指定された`CMFCToolBarButton`オブジェクトです。 (上書き[CMFCToolBarButton::CompareWith](../../mfc/reference/cmfctoolbarbutton-class.md#comparewith))。|  
|[CMFCToolBarMenuButton::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|  
|[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)|Windows メニュー ハンドルからツール バー メニューを初期化します。|  
|[CMFCToolBarMenuButton::CreateMenu](#createmenu)|ツール バー メニュー内のコマンドで構成される Windows メニューを作成します。 Windows メニューにハンドルを返します。|  
|[CMFCToolBarMenuButton::CreatePopupMenu](#createpopupmenu)|ポップアップ メニュー オブジェクトを作成します ( [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)) をツール バー メニューを表示します。|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](#enablequickcustomize)||  
|[CMFCToolBarMenuButton::GetCommands](#getcommands)|ツール バー メニューにコマンドのリストに読み取り専用でアクセスできます。|  
|[CMFCToolBarMenuButton::GetImageRect](#getimagerect)|ボタンのイメージの外接する四角形を取得します。|  
|[CMFCToolBarMenuButton::GetPaletteRows](#getpaletterows)|メニューがパレット モードの場合は、ポップアップ メニューで行の数を返します。|  
|[CMFCToolBarMenuButton::GetPopupMenu](#getpopupmenu)|ボタンに関連付けられているポップアップ メニュー オブジェクトへのポインターを返します。|  
|[CMFCToolBarMenuButton::HasButton](#hasbutton)||  
|[CMFCToolBarMenuButton::HaveHotBorder](#havehotborder)|ユーザーがボタンを選択したときに、ボタンの境界線を表示するかどうかを決定します。 (上書き[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder))。|  
|[CMFCToolBarMenuButton::IsBorder](#isborder)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](#isclickedonmenu)||  
|[CMFCToolBarMenuButton::IsDroppedDown](#isdroppeddown)|ポップアップ メニューが表示されるかどうかを決定します。|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|ユーザーが選択されたメニュー項目のサブメニューを開くことができるかどうかを調べるためにフレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::IsExclusive](#isexclusive)|かどうか、ボタンが排他モードでは、かどうか、ポップアップ メニューは開いたまま、ユーザーが別のツールバーまたはボタンの上にポインターを移動している場合でもを決定します。|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](#ismenupalettemode)|ポップアップ メニューがパレット モードになっているかどうかを判断します。|  
|[CMFCToolBarMenuButton::IsQuickMode](#isquickmode)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](#istearoffmenu)|ティアオフ バーが、ポップアップ メニューにあるかどうかを決定します。|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](#onaftercreatepopupmenu)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](#onbeforedrag)|ボタンをドラッグすることがあるかどうかを指定します。 (上書き[CMFCToolBarButton::OnBeforeDrag](../../mfc/reference/cmfctoolbarbutton-class.md#onbeforedrag))。|  
|[CMFCToolBarMenuButton::OnCalculateSize](#oncalculatesize)|指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|  
|[CMFCToolBarMenuButton::OnCancelMode](#oncancelmode)|処理するためにフレームワークによって呼び出される、 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615)メッセージです。 (上書き[CMFCToolBarButton::OnCancelMode](../../mfc/reference/cmfctoolbarbutton-class.md#oncancelmode))。|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](cmfctoolbarbutton-class.md#onchangeparentwnd))。|  
|[CMFCToolBarMenuButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|  
|[CMFCToolBarMenuButton::OnClickMenuItem](#onclickmenuitem)|ポップアップ メニューで、項目を選択するときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::OnContextHelp](#oncontexthelp)|親ツールバーが処理されるときに、フレームワークによって呼び出され、`WM_HELPHITTEST`メッセージです。 (上書き[CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp))。|  
|[CMFCToolBarMenuButton::OnDraw](#ondraw)|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|  
|[CMFCToolBarMenuButton::OpenPopupMenu](#openpopupmenu)|ユーザーが、ポップアップ メニューを開いたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarMenuButton::ResetImageToDefault](#resetimagetodefault)|ボタンに関連付けられているイメージを既定値に設定します。 (上書き[CMFCToolBarButton::ResetImageToDefault](../../mfc/reference/cmfctoolbarbutton-class.md#resetimagetodefault))。|  
|[CMFCToolBarMenuButton::SaveBarState](#savebarstate)|ツール バー ボタンの状態を保存します。 (上書き[CMFCToolBarButton::SaveBarState](../../mfc/reference/cmfctoolbarbutton-class.md#savebarstate))。|  
|[CMFCToolBarMenuButton::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|  
|[CMFCToolBarMenuButton::SetACCData](#setaccdata)|指定された設定`CAccessibilityData`ツール バー ボタンからデータをユーザー補助機能を持つオブジェクト。 (上書き[CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata))。|  
|[CMFCToolBarMenuButton::SetMenuOnly](#setmenuonly)|ツールバーにボタンを追加できるかどうかを指定します。|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)|ポップアップ メニューがパレット モードかどうかを指定します。|  
|[CMFCToolBarMenuButton::SetMessageWnd](#setmessagewnd)||  
|[CMFCToolBarMenuButton::SetRadio](#setradio)|強制的に、ツール バー メニュー ボタンが選択されていることを示すアイコンを表示します。|  
|[CMFCToolBarMenuButton::SetTearOff](#settearoff)|ティアオフを指定のポップアップ メニュー バーの ID。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](#drawdocumenticon)|メニュー ボタンのアイコンを描画します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw](#m_balwayscallownerdraw)|場合`TRUE`、フレームワークは、常に呼び出します[CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage)ボタンを描画するタイミングです。|  
  
## <a name="remarks"></a>コメント  
 A`CMFCToolBarMenuButton`メニューのサブメニューのあるメニュー項目、コマンドを実行するか、メニューを表示するボタンまたはメニューのみを表示するボタンとして表示されることができます。 イメージ、テキスト、メニュー ハンドルなどのパラメーターを指定して動作し、メニュー ボタンの外観を決定し、コマンド、コンス トラクターでボタンに関連付けられている ID`CMFCToolbarMenuButton::CMFCToolbarMenuButton`します。  
  
 派生したカスタム クラス、`CMFCToolbarMenuButton`クラスを使用する必要があります、 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロです。 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate)マクロは、アプリケーションの終了時にエラーを生成します。  
  
## <a name="example"></a>例  
 次の例では、構成、`CMFCToolBarMenuButton`オブジェクトです。 コードは、ドロップダウン メニューが、パレットのモードを指定して、ユーザーがメニュー バーのメニュー ボタンをドラッグしたときに作成されるティアオフ バーの ID を指定する方法を示しています。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#10;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarmenubutton.h  
  
##  <a name="cmfctoolbarmenubutton"></a>CMFCToolBarMenuButton::CMFCToolBarMenuButton  
 `CMFCToolBarMenuButton` オブジェクトを構築します。  
  
```  
CMFCToolBarMenuButton();
CMFCToolBarMenuButton(const CMFCToolBarMenuButton& src);

CMFCToolBarMenuButton(
    UINT uiID,  
    HMENU hMenu,  
    int iImage,  
    LPCTSTR lpszText=NULL,  
    BOOL bUserButton=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 既存の`CMFCToolBarMenuButton`オブジェクトにコピーされる`CMFCToolBarMenuButton`オブジェクトです。  
  
 [入力] `uiID`  
 ユーザーがボタンをクリックしたときに実行するコマンドの IDまたは ( `UINT`) コマンドを直接実行しません メニューのボタンの場合は-1。  
  
 [入力] `hMenu`  
 メニューへのハンドルまたは`NULL`ボタンには、メニューがない場合。  
  
 [入力] `iImage`  
 ボタンのイメージのインデックスこのボタンは、アイコンがありませんかによって指定されたコマンドのアイコンを使用する場合は-1`uiID`します。 インデックスが同じ`CMFCToolBarImages`アプリケーション内のオブジェクト。  
  
 [入力] `lpszText`  
 ツール バー メニュー ボタンのテキストです。  
  
 [入力] `bUserButton`  
 `TRUE`ボタンは、ユーザー定義のイメージを表示する場合`FALSE`ボタンで指定されたコマンドに関連付けられている定義済みのイメージを表示する場合`uiID`します。  
  
### <a name="remarks"></a>コメント  
 場合`uiID`が有効なコマンド ID、ボタンは、ユーザーがクリックしたときにそのコマンドを実行します。 場合`hMenu` メニューの無効なハンドルは、ボタンは、メニューが表示されたら、ツールバーやサブメニューに表示されるときにドロップダウン メニューを提供します。 両方`uiID`と`hMenu`が有効で、ボタンは、ユーザーがクリックしたときに、コマンドが実行される部分とはドロップダウン メニュー、ユーザーがクリックしたときにある下矢印の部分の分割ボタン。 ただし場合、`hMenu`有効ですが、ユーザーは、ボタンがメニューに挿入されたときに、コマンドを実行する ボタンをクリックしてできません。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCToolBarMenuButton`クラスです。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#9;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_2.cpp)]  
  
##  <a name="comparewith"></a>CMFCToolBarMenuButton::CompareWith  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `other`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="copyfrom"></a>CMFCToolBarMenuButton::CopyFrom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createfrommenu"></a>CMFCToolBarMenuButton::CreateFromMenu  
 Windows メニュー ハンドルからツール バー メニューを初期化します。  
  
```  
virtual void CreateFromMenu(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
 メニューへのハンドル。  
  
### <a name="remarks"></a>コメント  
 ツールバーのメニュー ボタンには、ドロップダウン サブメニューを表示できます。  
  
 フレームワークでは、メニューのサブメニューにコマンドを初期化するには、このメソッドを呼び出します。  
  
##  <a name="createmenu"></a>CMFCToolBarMenuButton::CreateMenu  
 ツール バー メニュー内のコマンドで構成されるメニューを作成します。 メニューにハンドルを返します。  
  
```  
virtual HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 識別するハンドル、メニューの 場合は成功します。 `NULL`ツール バー メニュー ボタンに関連付けられているコマンドの一覧が空の場合。  
  
### <a name="remarks"></a>コメント  
 メニューの生成方法をカスタマイズする派生クラスでは、このメソッドをオーバーライドすることができます。  
  
##  <a name="createpopupmenu"></a>CMFCToolBarMenuButton::CreatePopupMenu  
 作成、`CMFCPopupMenu`ツール バー メニューを表示するオブジェクト。  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCPopupMenu`をツール バー メニュー ボタンに関連付けられたドロップダウン メニューを表示するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ボタンに関連付けられたドロップダウン メニューの表示を準備するために、フレームワークによって呼び出されます。  
  
 既定の実装を構築して、新しい返すだけ`CMFCPopupMenu`オブジェクトです。 派生型を使用する場合は、このメソッドをオーバーライド[CMFCPopupMenu クラス](cmfcpopupmenu-class.md)または追加の初期化を実行します。  
  
##  <a name="drawdocumenticon"></a>CMFCToolBarMenuButton::DrawDocumentIcon  
 メニュー ボタンのドキュメント アイコンを描画します。  
  
```  
void DrawDocumentIcon(
    CDC* pDC,  
    const CRect& rectImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectImage`  
 イメージの外接する四角形の座標です。  
  
 [入力] `hIcon`  
 アイコンへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドキュメントのアイコンを受け取りで指定された領域の中央に配置 メニューのボタンの描画`rectImage`します。  
  
##  <a name="enablequickcustomize"></a>CMFCToolBarMenuButton::EnableQuickCustomize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableQuickCustomize();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasbutton"></a>CMFCToolBarMenuButton::HasButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="havehotborder"></a>CMFCToolBarMenuButton::HaveHotBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isborder"></a>CMFCToolBarMenuButton::IsBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isclickedonmenu"></a>CMFCToolBarMenuButton::IsClickedOnMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsClickedOnMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isquickmode"></a>CMFCToolBarMenuButton::IsQuickMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsQuickMode();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcommands"></a>CMFCToolBarMenuButton::GetCommands  
 ツール バー メニューにコマンドのリストに読み取り専用でアクセスできます。  
  
```  
const CObList& GetCommands() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Const 参照、 [CObList クラス](../../mfc/reference/coblist-class.md)のコレクションを含むオブジェクトを[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ツールバーのメニュー ボタンには、サブメニューを表示できます。 コンス トラクターは、またはサブメニューにコマンドの一覧を提供できます[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)メニューへのハンドルとして ( `HMENU`)。 派生したオブジェクトの一覧に、メニューが変換[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)内部に格納されていると`CObList`オブジェクトです。 この一覧は、このメソッドを呼び出すことによってアクセスできます。  
  
##  <a name="getimagerect"></a>CMFCToolBarMenuButton::GetImageRect  
 ボタンのイメージの外接する四角形を取得します。  
  
```  
void GetImageRect(CRect& rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectImage`  
 参照、`CRect`イメージに外接する四角形の座標を受け取るオブジェクトです。  
  
##  <a name="getpaletterows"></a>CMFCToolBarMenuButton::GetPaletteRows  
 メニューがパレット モードの場合は、ドロップダウン メニューで行の数を返します。  
  
```  
int GetPaletteRows() const;  
```  
  
### <a name="return-value"></a>戻り値  
 パレット内の行の数。  
  
### <a name="remarks"></a>コメント  
 メニュー ボタンがパレット モードに設定されている場合は、メニュー項目が一定数の行で複数の列に表示されます。 行の数を取得するには、このメソッドを呼び出します。 有効にするか、パレット モードを無効にしてを使用して行の数を指定[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)します。  
  
##  <a name="getpopupmenu"></a>CMFCToolBarMenuButton::GetPopupMenu  
 ポインターを返す、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)をボタンのドロップダウン メニューを表すオブジェクト。  
  
```  
CMFCPopupMenu* GetPopupMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)フレームワーク、ツール バー メニュー ボタンのサブメニューを描画するときに作成されたオブジェクト`NULL`サブメニューが表示されていない場合。  
  
### <a name="remarks"></a>コメント  
 ツールバーのメニュー ボタンには、ドロップダウン メニューが表示されたら、ボタンを作成、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)メニューを表すオブジェクト。 ポインターを取得するには、このメソッドを呼び出して、`CMFCPopupMenu`オブジェクトです。 返されたポインターを保存しないでためは一時的であり、ユーザーがドロップダウン メニューを閉じると無効になりますに。  
  
##  <a name="isdroppeddown"></a>CMFCToolBarMenuButton::IsDroppedDown  
 ポップアップ メニューが現在表示されているかどうかを示します。  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツール バー メニュー ボタンにサブメニューが表示される場合それ以外の場合`FALSE`します。  
  
##  <a name="isemptymenuallowed"></a>CMFCToolBarMenuButton::IsEmptyMenuAllowed  
 メニュー項目が空のサブメニューを表示するかどうかを指定します。  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームワークでは、サブメニューが空の場合でも、現在選択されているメニュー項目からサブメニューを開く場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ユーザーは、現在選択されているメニュー項目のサブメニューを開こうとすると、このメソッドを呼び出します。 サブメニューが空の場合と`IsEmptyMenuAllowed`返します`FALSE`サブメニューを開くことはありません。  
  
 既定の実装では、`FALSE` が返されます。 この動作をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="isexclusive"></a>CMFCToolBarMenuButton::IsExclusive  
 ボタンは排他モードにするかどうかを示します。  
  
```  
virtual BOOL IsExclusive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンが排他モードで動作している場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ユーザーは、ボタンのポップアップ メニューを開き、別のツールバーまたはメニュー ボタンの上でマウス ポインターを移動と、ボタンが排他モードでない限り、ポップアップ メニューが閉じます。  
  
 既定の実装を常に`FALSE`します。 排他モードを有効にする場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="ismenupalettemode"></a>CMFCToolBarMenuButton::IsMenuPaletteMode  
 ドロップダウン メニューがパレット モードになっているかどうかを判断します。  
  
```  
BOOL IsMenuPaletteMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`それ以外の場合、パレット モードが有効な場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 メニュー ボタンがパレット モードに設定されている場合は、一定数の行で複数の列にメニュー項目が表示されます。 行の数を取得するには、このメソッドを呼び出します。 有効にするかを呼び出してパレット モードを無効にする[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)します。  
  
##  <a name="istearoffmenu"></a>CMFCToolBarMenuButton::IsTearOffMenu  
 ドロップダウン メニューにティアオフ バーがあるかどうかを示します。  
  
```  
virtual BOOL IsTearOffMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ツール バー メニュー ボタンにティアオフ バーです。それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ティアオフ機能を有効にし、ティアオフ設定 ID に、バーを呼び出す[CMFCToolBarMenuButton::SetTearOff](#settearoff)します。  
  
##  <a name="m_balwayscallownerdraw"></a>CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw  
 フレームワークと常に記述するかどうかを示す[CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage)ボタンを描画するタイミングです。  
  
```  
static BOOL m_bAlwaysCallOwnerDraw;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数を設定すると`TRUE`、ボタンは常に呼び出します[CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage)ボタンにイメージを表示します。 `m_bAlwaysCallOwnerDraw`は`FALSE`、ボタン自体は、イメージはあらかじめ定義されている場合に、イメージを描画します。 それ以外の場合、それを呼び出す`OnDrawMenuImage`します。  
  
##  <a name="onaftercreatepopupmenu"></a>CMFCToolBarMenuButton::OnAfterCreatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterCreatePopupMenu();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onbeforedrag"></a>CMFCToolBarMenuButton::OnBeforeDrag  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncalculatesize"></a>CMFCToolBarMenuButton::OnCalculateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `sizeDefault`  
 [入力] `bHorz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncancelmode"></a>CMFCToolBarMenuButton::OnCancelMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarMenuButton::OnChangeParentWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclick"></a>CMFCToolBarMenuButton::OnClick  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 [入力] `bDelay`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclickmenuitem"></a>CMFCToolBarMenuButton::OnClickMenuItem  
 ボックスの一覧で項目を選択するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClickMenuItem();
```  
  
### <a name="return-value"></a>戻り値  
 `FALSE`framework は既定のメニュー項目の処理は続行する場合それ以外の場合`TRUE`します。 既定の実装を常に`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 ユーザーには、メニュー項目がクリックすると、フレームワークは、その項目に関連付けられているコマンドを実行します。  
  
 メニュー項目の処理をカスタマイズする上書き`OnClickMenuItem`から派生したクラスで`CMFCToolBarMenuButton`クラスです。 またをオーバーライドする必要があります[CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu)と派生クラスのインスタンスを持つ特別な処理を必要とするメニュー ボタンを置換します。  
  
##  <a name="oncontexthelp"></a>CMFCToolBarMenuButton::OnContextHelp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>CMFCToolBarMenuButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `pImages`  
 [入力] `bHorz`  
 [入力] `bCustomizeMode`  
 [入力] `bHighlight`  
 [入力] `bDrawBorder`  
 [入力] `bGrayDisabledButtons`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarMenuButton::OnDrawOnCustomizeList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `rect`  
 [入力] `bSelected`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="openpopupmenu"></a>CMFCToolBarMenuButton::OpenPopupMenu  
 ユーザーがツール バー メニュー ボタンのドロップダウン メニューを開いたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OpenPopupMenu(CWnd* pWnd=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 ドロップ ダウン メニュー コマンドを受信する期間を指定します。 できます`NULL`ツール バー メニュー ボタンは、親ウィンドウを持つ場合だけです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ときに、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが作成され、それ以外の場合、正常に開かれた`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、ユーザーがツール バー メニュー ボタンのドロップダウン メニューを開いたとき、framework によって呼び出されます。  
  
##  <a name="resetimagetodefault"></a>CMFCToolBarMenuButton::ResetImageToDefault  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="savebarstate"></a>CMFCToolBarMenuButton::SaveBarState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ツール バー ボタンをドラッグ アンド ドロップ操作の結果として作成するときに、このメソッドを呼び出します。 このメソッドは、 [CMFCPopupMenu::SaveState](../../mfc/reference/cmfcpopupmenu-class.md#savestate)最上位レベルのポップアップ メニューで、そのメニューを作成し直す、ポップアップ メニューのボタンの親のメソッドです。  
  
##  <a name="serialize"></a>CMFCToolBarMenuButton::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setaccdata"></a>CMFCToolBarMenuButton::SetACCData  
 リボン要素のアクセシビリティ データを設定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 リボン要素の親ウィンドウ。  
  
 `data`  
 リボン要素のアクセシビリティ データ。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドはリボン要素のアクセシビリティ データを設定し、常に `TRUE`を返します。 アクセシビリティ データを設定し、成功または失敗を示す値を返すようにするには、このメソッドをオーバーライドします。  
  
##  <a name="setmenuonly"></a>CMFCToolBarMenuButton::SetMenuOnly  
 有効なコマンド ID とサブメニューの両方があると、メニュー ボタンまたは分割ボタンとボタンを描画するかどうかを指定します。  
  
```  
void SetMenuOnly(BOOL bMenuOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMenuOnly`  
 `TRUE`有効なコマンド ID と、サブメニューの両方があるときに、メニュー ボタンとしては、このボタンを表示する`FALSE`有効なコマンド ID とサブメニューの両方があるときに、分割ボタンとしては、このボタンを表示します。  
  
### <a name="remarks"></a>コメント  
 通常、ツールバーのメニュー ボタンは、サブメニューとコマンド ID の両方を持っている場合は、下向きの矢印ボタンのメイン ボタンと、接続されているが分割ボタンのように、メニューが表示されます。 このメソッドを呼び出す場合と`bMenuOnly`は`TRUE`ボタンに下向きの矢印付きの&1; つのメニュー ボタンを代わりに、ボタンを表示します。 フレームワークのいずれかのモードのボタンの矢印のない部分が、コマンドを実行して、ユーザーがクリックして、ユーザーは、どちらのモードにある矢印をクリックすると、サブメニューが開きます。  
  
##  <a name="setmenupalettemode"></a>CMFCToolBarMenuButton::SetMenuPaletteMode  
 ドロップダウン メニューがパレット モードかどうかを指定します。  
  
```  
void SetMenuPaletteMode(
    BOOL bMenuPaletteMode=TRUE,  
    int nPaletteRows=1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMenuPaletteMode`  
 ドロップダウン メニューがパレット モードかどうかを指定します。  
  
 [入力] `nPaletteRows`  
 パレット内の行の数です。  
  
### <a name="remarks"></a>コメント  
 パレット モードでは、すべてのメニュー項目は複数列のパレットとして表示されます。 使用して行の数を指定する`nPaletteRows`です。  
  
##  <a name="setmessagewnd"></a>CMFCToolBarMenuButton::SetMessageWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMessageWnd(CWnd* pWndMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndMessage`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setradio"></a>CMFCToolBarMenuButton::SetRadio  
 オンになっているときに、ラジオ ボタン スタイルのアイコンを表示するツール バー メニュー ボタンを設定します。  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>コメント  
 オンになっているときにメニュー ボタンが描画されると、それを呼び出す[CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)チェック マーク アイコンを描画します。 既定では、`OnDrawMenuCheck`要求の現在のビジュアル マネージャーは、チェック ボックスを描画メニュー ボタンにあるチェック マークのスタイルを設定します。 このメソッドを呼び出すと、現在のビジュアル マネージャーは代わりに、ラジオ ボタンのスタイルのチェック マークをメニュー ボタンを描画します。 この変更を元に戻すことはできません。  
  
 このメソッドを呼び出すし、メニュー ボタンが表示されている、更新されます。  
  
##  <a name="settearoff"></a>CMFCToolBarMenuButton::SetTearOff  
 ドロップダウン メニューの切り取りバーの ID を指定します。  
  
```  
virtual void SetTearOff(UINT uiBarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiBarID`  
 新しいティアオフ指定バー ID  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、ユーザーがメニュー バーのメニュー ボタンをドラッグしたときに作成されるティアオフ バーの ID を指定します。 場合、`uiBarID`パラメーターが 0 のユーザーがメニュー ボタン ティアオフことはできません場合、。  
  
 呼び出す[CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)ティアオフ メニュー機能をアプリケーションで有効にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
