---
title: "CMFCOutlookBarTabCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl class
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
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
ms.openlocfilehash: 16de4287a2b3a6352fb4fc560b9c8eec2ba766d1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Microsoft Outlook の **ナビゲーション ウィンドウ** と同じ外観を持つタブ コントロールです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|既定のコンストラクター|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Outlook バーに新しいタブとしては、Windows コントロールを追加します。|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|フレームワークによって呼び出されますときユーザーに表示されるボックスのサイズを調べるために名前を変更、タブをクリックします。 (`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします)。|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|現在表示されているよりも少ない Outlook バー タブ ページのボタンを表示できる場合を判断するのにサイズ変更操作時にフレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|現在表示されているよりもさらに Outlook バー タブ ページ ボタンを表示できる場合を判断するのにサイズ変更操作時にフレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Outlook バー タブ コントロールを作成します。|  
|`CMFCOutlookBarTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|アクティブなタブの切り替え中に発生するアニメーションが有効になっているかどうかを指定します。|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|ユーザーが Outlook バーのタブのボタンにテキスト ラベルを変更できるかどうかを指定します。 (上書き[CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit))。|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|ユーザーが Outlook バー ペイン上のボタン間をスクロールできるボタンを有効にするために、フレームワークによって呼び出されます。|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|指定したポイントを含むウィンドウを識別します。 (上書き[CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd))。|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook タブ コントロールの境界線のサイズを返します。|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|タブ コントロールのタブ領域の位置とサイズを取得します。 (上書き[CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea))。|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|アクティブなタブの切り替え中に発生するアニメーションが有効になっているかどうかを決定します。|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Outlook バー タブ コントロールが Microsoft Outlook 2003 のエミュレーション モードのかどうかを判断します。|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|かどうか、ポイントは、タブ領域の内部を決定します。 (上書き[CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea))。|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|タブが取り外し可能かどうかを決定します。 (上書き[CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable))。|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|タブが挿入または削除されたときに、フレームワークによって呼び出されます。 (`CMFCBaseTabCtrl::OnChangeTabs` をオーバーライドします)。|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|表示されているタブ ページのボタンの数を削減するためにフレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|表示されているタブ ページのボタンの数を増やすために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|表示、**ナビゲーション ウィンドウ オプション**ダイアログ。|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|タブ コントロールの内部のレイアウトを再計算します。 (上書き[CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout))。|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|アクティブなタブを設定します。 (上書き[CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab))。|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook タブ コントロールの境界線のサイズを設定します。|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Outlook バーのタブのボタンのテキスト ラベルの配置を設定します。|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 モードで Outlook バーの下に表示されるアイコンを含むビットマップを設定 (表示[があります](../../mfc/reference/cmfcoutlookbar-class.md))。|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>コメント  
 ドッキングのサポートのある Outlook バーを作成するには、使用、 `CMFCOutlookBar` Outlook バー タブ コントロールをホストするオブジェクト。 詳細については、次を参照してください。[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、初期化、`CMFCOutlookBarTabCtrl`オブジェクトを多様なメソッドを使用して、`CMFCOutlookBarTabCtrl`クラスです。 この例では、Outlook バーのタブ ページのボタンにテキスト ラベルを一括編集の有効化、アニメーションを有効にする、ユーザーが Outlook バー ペインの各ボタンをスクロールし、Outlook のタブ コントロールの境界線のサイズを設定し、Outlook バーのタブのボタンのテキスト ラベルの配置を設定できるようにスクロール ハンドルを有効にする方法を示します。 このコード スニペットの一部である、 [Outlook のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl  
 Outlook バーに新しいタブとしては、Windows コントロールを追加します。  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndCtrl`  
 追加するためのコントロールへのポインター。  
  
 [入力] `lpszName`  
 タブの名前を指定します。  
  
 [入力] `bDetachable`  
 場合`TRUE`ページは、取り外し可能として作成されます。  
  
 [入力] `nImageID`  
 新しいタブに表示されるイメージの内部のイメージ リストのイメージのインデックス。  
  
 [入力] `dwControlBarStyle`  
 指定、afx _ `CBRS_`* ラップされたドッキング ペインのスタイル。  
  
### <a name="remarks"></a>コメント  
 Outlook バーの新しいページにコントロールを追加するのにには、この関数を使用します。  
  
 この関数で内部的に呼び出す[CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)します。  
  
 設定した場合`bDetachable`に`TRUE`、`AddControl`内部的に作成、`CDockablePaneAdapter`オブジェクトを追加したコントロールをラップします。 ランタイム クラスにタブ付きウィンドウのランタイム クラスが自動的に設定して`CMFCOutlookBar`とフローティング フレームのランタイム クラス`CMultiPaneFrameWnd`します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`AddControl`メソッドで、`CMFCOutlookBarTabCtrl`クラスです。 このコード スニペットの一部である、 [Outlook のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 現在表示されているよりも少ない Outlook バー タブ ページのボタンを表示できるかどうかを決定する操作をサイズ変更時にフレームワークによって呼び出されます。  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`1 つ以上のボタンがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 Outlook バー タブ コントロールは、動的に追加またはタブによって、どのくらいの領域が利用可能な表示から削除します。 このメソッドは、そのプロセスを支援するために、フレームワークによって使用されます。  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 現在表示されているよりもさらに Outlook バー タブ ページ ボタンを表示するかどうかを判断する操作をサイズ変更時にフレームワークによって呼び出されます。  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`。 現在表示されていないボタンがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 Outlook バー タブ コントロールは動的に追加またはタブによって、どのくらいの領域が利用可能な表示から削除します。 このメソッドは、そのプロセスを支援するために、フレームワークによって使用されます。  
  
##  <a name="create"></a>CMFCOutlookBarTabCtrl::Create  
 Outlook バー タブ コントロールを作成します。  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 初期サイズと位置をピクセル単位で指定します。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。 `NULL` にすることはできません。  
  
 [入力] `nID`  
 コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 コントロールが正常に作成されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、outlook バー タブのコントロールが作成[があります](../../mfc/reference/cmfcoutlookbar-class.md)コントロール、`WM_CREATE`プロセスのメッセージ。  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 アクティブなタブの切り替え中に発生するアニメーションが有効になっているかどうかを指定します。  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 アニメーションを有効または無効にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 アニメーションを無効にするには、この関数を呼び出します。 タブ ページを開くと、ページのキャプションはアニメーションが有効な場合に単位の上下をスライドします。 すぐにアニメーションを無効にした場合に、ページがアクティブです。  
  
 既定では、アニメーションは有効です。  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 ユーザーが Outlook バーのタブ ページのボタンのテキスト ラベルを変更できるかどうかを指定します。  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 場合`TRUE`、テキスト ラベルの一括編集を有効にします。 場合`FALSE`、埋め込み先編集を無効にします。  
  
### <a name="remarks"></a>コメント  
 この関数では、有効またはインプレースでのタブ ページのボタンにテキスト ラベルの編集を無効にします。 既定では、インプレース編集が無効になります。  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 ユーザーが Outlook バー ペインの各ボタンをスクロールできるようにスクロール ハンドルを有効にするために、フレームワークによって呼び出されます。  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 スクロール ボタンを表示するかどうかを決定します。  
  
 [入力] `bIsUp`  
 上部のスクロール バーが表示されるかどうかを決定します。  
  
 [入力] `bIsDown`  
 下部のスクロール バーが表示されるかどうかを決定します。  
  
### <a name="remarks"></a>コメント  
 スクロール ボタンの表示を有効にします。 スクロール ボタンを復元するアクティブなタブが変更されたときに、このメソッドは、フレームワークによって呼び出されます。  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Outlook タブ コントロールの境界線のサイズを返します。  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 境界線のサイズ (ピクセル)。  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 アクティブなタブの切り替え中に発生するアニメーションが有効になっているかどうかを指定します。  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーションが有効な場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す、 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)を有効にする、またはアニメーションを無効にします。  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Outlook バー タブ コントロールが Microsoft Outlook 2003 のエミュレーション モードであるかどうかを判断します。  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`Outlook バー タブ コントロールが Outlook 2003 モードである場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 この値によって設定されます[CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)します。  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 表示されているタブ ページのボタンの数を削減するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールがサイズ変更時に表示されるページ タブのボタンの数を調整します。  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 表示されているタブ ページのボタンの数を増やすために、フレームワークによって呼び出されます。  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールがサイズ変更時に表示されているタブ ページのボタンの数を調整します。  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 表示、**ナビゲーション ウィンドウ オプション** ダイアログ ボックス。  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>コメント  
 **ナビゲーション ウィンドウ オプション** ダイアログ ボックスを使ってタブ ページのボタンが、表示するかを選択し、順序が表示されます。  
  
 ユーザーを選択すると、フレームワークによって呼び出されます、**ナビゲーション ウィンドウ オプション**コントロールのカスタマイズ メニューのメニュー項目です。  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 アクティブなタブを設定します。 アクティブなタブは、そのコンテンツが表示されると、開かれている&1; つです。  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTab`  
 開く タブの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したタブが正常に開かれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アクティブなタブの設定の視覚的効果は、アニメーションが有効にするかどうかによって異なります。 詳細については、次を参照してください。 [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)します。  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Outlook タブ コントロールの境界線のサイズを設定します。  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nBorderSize`  
 新しい境界線のサイズをピクセル単位で指定します。  
  
### <a name="remarks"></a>コメント  
 新しい境界線のサイズを設定し、outlook のウィンドウ レイアウトを再計算します。  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Outlook バーのタブのボタンのテキスト ラベルの配置を設定します。  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiAlign`  
 テキストの配置を指定します。  
  
 [入力] `bRedraw`  
 場合`TRUE`outlook のウィンドウが再描画されます。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、ページのボタンのテキストの配置を変更できます。  
  
 `uiAlign`次の値のいずれかを指定できます。  
  
|定数|説明|  
|--------------|-------------|  
|TA_LEFT|左揃え|  
|TA_CENTER|中央揃え|  
|TA_RIGHT|右揃え|  
  
 既定値は、TA_CENTER です。  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Outlook 2003 モードで Outlook バーの下に表示されるアイコンを含むビットマップを設定します。  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 読み込むイメージのリソース ID を指定します。  
  
 [入力] `cx`  
 イメージ リストには、ピクセル単位でイメージの幅を指定します。  
  
 [入力] `clrTransp`  
 透明色を指定する RGB 値。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`成功した場合、それ以外の場合を返します`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、Microsoft Office 2003 モードでのツール バー ボタンに表示されるイメージがイメージ リストをアタッチできます。 イメージ インデックス ページのインデックスに対応します。  
  
 このメソッドは、Microsoft Office 2003 モードではない場合は呼び出されません必要があります。 詳細については、次を参照してください。[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nVisiblePageButtons`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [あります。](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)

