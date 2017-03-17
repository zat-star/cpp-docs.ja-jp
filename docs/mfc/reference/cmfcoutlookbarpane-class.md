---
title: "CMFCOutlookBarPane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- Dock method
- IsChangeState method
- SmartUpdate method
- OnBeforeFloat method
- RestoreOriginalstate method
- CMFCOutlookBarPane class
- CanBeRestored method
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
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
ms.openlocfilehash: da4fab1a6d94e962090f21414062dc2da0c9482c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbarpane-class"></a>CMFCOutlookBarPane クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 派生したコントロール[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)を Outlook バーに挿入できる ([があります](../../mfc/reference/cmfcoutlookbar-class.md))。 Outlook バー ペインには、大きいボタンの列があります。 ボタンのリストがペインより長い場合、ユーザーはリストを上下にスクロールできます。 ユーザーが Outlook バー ペインを Outlook バーから切り離すと、そのペインをフローティング状態にするかメイン フレーム ウィンドウにドッキングできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|既定のコンストラクター|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Outlook バー ペインには、ボタンを追加します。|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|別のウィンドウまたはフレーム ウィンドウのウィンドウをドッキングできるかどうかを決定します。 (上書き[CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached))。|  
|`CMFCOutlookBarPane::CanBeRestored`|システムが、カスタマイズ後ツールバーを元の状態に復元できるかどうかを決定します。 (上書き[CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored))。|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Outlook バー ペインのイメージで使用されているリソースを解放します。|  
|[CMFCOutlookBarPane::Create](#create)|Outlook バー ペインを作成します。|  
|`CMFCOutlookBarPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCOutlookBarPane::Dock`|Outlook バー ペインをドッキングするのには、フレームワークによって呼び出されます。 (`CPane::Dock` をオーバーライドします)。|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|ページで、またはボタンをクリックして、Outlook バー ペインのスクロール バーの矢印がボタンの一覧を進めるかどうかを示します。|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Outlook バー ペインの正規 (選択されていない) テキストの色を返します。|  
|`CMFCOutlookBarPane::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Outlook バー ペインの読み込まれた背景イメージがあるかどうかを決定します。|  
|`CMFCOutlookBarPane::IsChangeState`|浮動ペインをドッキングできるかどうかを決定します。 (`CPane::IsChangeState` をオーバーライドします)。|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|ボタンが強調表示されている背景画像が表示されるときにボタンの境界線が影付きにするかどうかを決定します。|  
|`CMFCOutlookBarPane::OnBeforeFloat`|ペインが浮動小数点数に、フレームワークによって呼び出されます。 (上書き[CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat))。|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|指定されたコマンド ID を持つボタンを削除します。|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|ツール バーを元の状態に戻します。 (上書き[CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate))。|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|背景色を設定します。|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|背景画像を設定します。|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|ボタンの元のセットを Outlook バー ペインをリセットします。|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Outlook バー ペインのボタンの周囲に使用するパディングのピクセル数を設定します。|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Outlook バー ペインの通常および強調表示されているテキストの色を設定します。|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Outlook バー ペインの透明色を設定します。|  
|`CMFCOutlookBarPane::SmartUpdate`|Outlook バーを更新するには、内部的に使用します。 (`CMFCToolBar::SmartUpdate` をオーバーライドします)。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|カスタマイズ モードで表示するショートカット メニュー項目を指定します。|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Outlook バー ペインからすべてのボタンを削除します。 (上書き[CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons))。|  
  
## <a name="remarks"></a>コメント  
 Outlook バーを実装する方法については、次を参照してください。[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
 Outlook バーの例は、OutlookDemo サンプル プロジェクトを参照してください。  
  
## <a name="example"></a>例  
 次の例では、さまざまな方法を使用して、`CMFCOutlookBarPane`クラスです。 この例では、Outlook バー ペインを作成、ページのスクロール モードを有効にする、ドッキングを有効にする、および Outlook バーの背景色を設定する方法を示します。 このコード スニペットの一部である、 [Outlook の複数のビューのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&#3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&4;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoutlookbarpane.h  
  
##  <a name="addbutton"></a>CMFCOutlookBarPane::AddButton  
 Outlook バー ペインには、ボタンを追加します。  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiImage`  
 ビットマップのリソース識別子を指定します。  
  
 [入力] `lpszLabel`  
 ボタンのテキストを指定します。  
  
 [入力] `iIdCommand`  
 ボタン コントロールの ID を指定します  
  
 [入力] `iInsertAt`  
 ボタンを挿入する位置を示すページを outlook バーの上には、0 から始まるインデックスを指定します。  
  
 [入力] `uiLabel`  
 文字列リソース ID  
  
 [入力] `szBmpFileName`  
 読み込むディスク イメージ ファイルの名前を指定します。  
  
 [入力] `szLabel`  
 ボタンのテキストを指定します。  
  
 [入力] `hBmp`  
 ボタンのビットマップへのハンドル。  
  
 [入力] `hIcon`  
 ボタンのアイコンへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンが正常に追加された場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 Outlook バーのページに新しいボタンを挿入するのにには、このメソッドを使用します。 アプリケーション リソースとは、ディスク ファイルから、ボタンのイメージを読み込むことができます。  
  
 ページ ID が指定された場合`uiPageID`-1 で、ボタンは、最初のページに挿入されます。  
  
 によってインデックスが指定された場合`iInsertAt`-1 で、ボタンがページの末尾に追加します。  
  
##  <a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Outlook バー ペインのイメージで使用されているリソースを解放します。  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを直接呼び出す[CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)、Outlook バー ペインで使用されるイメージで呼び出されます。  
  
##  <a name="create"></a>CMFCOutlookBarPane::Create  
 Outlook バー ペインを作成します。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 Outlook バー ペインのコントロールの親ウィンドウを指定します。 `NULL` にすることはできません。  
  
 [入力] `dwStyle`  
 ウィンドウ スタイル。  ウィンドウ スタイルの一覧は、次を参照してください。[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 [入力] `uiID`  
 コントロールの id。 有効にするのには一意でなければ、コントロールの状態を保存します。  
  
 [入力] `dwControlBarStyle`  
 Outlook バーからデタッチされるときに、Outlook バー ペインのコントロールの動作を定義する特殊なスタイルを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CMFCOutlookBarPane`オブジェクト、最初に、コンス トラクターを呼び出すし、し、呼び出す`Create`、Outlook バー ペインのコントロールを作成およびそれにアタッチする、`CMFCOutlookBarPane`オブジェクトです。  
  
 詳細については`dwControlBarStyle`を参照してください[CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)します。  
  
##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 カスタマイズ モードで表示するショートカット メニュー項目を指定します。  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ユーザーがクリックしたツール バー ボタンへのポインター。  
  
 [入力] `pPopup`  
 ショートカット メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`場合は、ショートカット メニューが表示されているそれ以外の場合にする必要があります`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、カスタマイズ モードで表示するフレームワークの標準のショートカット メニューを変更するには、このメソッドをオーバーライドします。  
  
 既定の実装は、カスタマイズ モードをチェック ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) に設定されている場合、 `TRUE`、以外のすべてのショートカット メニュー項目を無効に**削除**します。 次に、入力パラメーターを渡すのみ`CMFCToolBar::EnableContextMenuItems`します。  
  
> [!NOTE]
> *コンテキスト メニュー*がショートカット メニューのシノニムです。  
  
##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Outlook バー ペインのスクロール バーの矢印がページごとまたは ボタンをクリックしてボタンのボタンの一覧を進めるかどうかを示します。  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPageScroll`  
 場合`TRUE`ページのスクロール モードを有効にします。 場合`FALSE`ページのスクロール モードを無効にします。  
  
##  <a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 標準が返されます (つまり、選択されていない) Outlook バー ペインのテキストの色。  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色の値として現在のテキストの色。  
  
### <a name="remarks"></a>コメント  
 使用[CMFCOutlookBarPane::SetTextColor](#settextcolor)を Outlook バーの現在の (正規および選択された) テキストの色を設定します。 既定のテキスト色を取得するには呼び出すことによって、 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)関数を`COLOR_WINDOW`インデックス。  
  
##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Outlook バー ペインの読み込まれた背景イメージがあるかどうかを決定します。  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`表示する背景イメージがある場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 背景画像を追加するを呼び出します[CMFCOutlookBarPane::SetBackImage](#setbackimage)関数です。  
  
 使用して指定された色と背景を描画の背景画像がない場合は、 [CMFCOutlookBarPane::SetBackColor](#setbackcolor)します。  
  
##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 ボタンが強調表示されている背景画像が表示されるときにボタンの境界線が影付きにするかどうかを決定します。  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンの境界線が影付きの場合それ以外の場合`FALSE`します。  
  
##  <a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Outlook バー ペインからすべてのボタンを削除します。  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>CMFCOutlookBarPane::RemoveButton  
 指定されたコマンド ID を持つボタンを削除します。  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIdCommand`  
 削除するボタンのコマンド ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンが正常に削除された場合`FALSE`場合は、指定されたコマンド ID が無効です。  
  
##  <a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Outlook バーの背景色を設定します。  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 新しい背景色を指定します。  
  
### <a name="remarks"></a>コメント  
 Outlook バーの現在の背景色を設定するには、この関数を呼び出します。 背景色は、背景画像がない場合にのみ使用されます。  
  
##  <a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 背景画像を設定します。  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiImageID`  
 イメージ リソース ID を指定します  
  
### <a name="remarks"></a>コメント  
 Outlook を設定するには、このメソッドを呼び出すバーの背景イメージ。 背景イメージの一覧を管理して埋め込まれた[CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)オブジェクトです。  
  
##  <a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 ボタンの元のセットを Outlook バー ペインをリセットします。  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Outlook バーのボタンを元のセットに復元します。 このメソッドはのように、 `CMFCOutlookBarPane::RestoreOriginalstate`Outlook バー ペインを再描画が開始されない点が異なります。  
  
##  <a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Outlook バー ペインのボタンの周囲に使用するパディングのピクセル数を設定します。  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Outlook バー ペインの通常および強調表示されているテキストの色を設定します。  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrRegText`  
 選択されていないテキストを新しい色を指定します。  
  
 [入力] `clrSelText`  
 新しい選択したテキストの色を指定します。  
  
##  <a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor  
 Outlook バー ペインの透明色を設定します。  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 新しい透過色を指定します。  
  
### <a name="remarks"></a>コメント  
 透明な画像を表示するには、透明色が必要です。 出現するすべてのイメージでは、この色は、背景色で描画されます。  前景色および背景のイメージの描画はありません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [あります。](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

