---
title: "CMFCPopupMenuBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCPopupMenuBar class
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46f86035fecc16c45e01a1c70cdde610093d377b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar クラス
ポップアップ メニューに埋め込まれたメニュー バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|すぐに、ウィンドウのレイアウトを再計算します。 (上書き[CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate))。|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|指定されたメニュー リソースからのポップアップ メニュー項目を読み込みます。|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|遅延のポップアップ メニュー ボタンを閉じます。|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|ポップアップ メニュー ボタンのメニューを作成します。|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|指定した点がどこにあるツールバーを検索します。|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|メニュー ボタンのイメージのサイズを示します。|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|既定のメニュー項目の識別子を返します。|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|最後に呼び出したのメニュー コマンドのインデックスを取得します。|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|ポップアップ メニュー バーの行オフセットを取得します。|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|指定されたメニューからのポップアップ メニュー ボタンをインポートします。|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|ポップアップ メニュー バーがドロップ ダウン リスト モードであるかどうかを示します。|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|ポップアップ メニュー バーがパレット モードかどうかを示します。|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|リボン パネルであるかどうかを示します (`FALSE`既定)。|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|通常モードでリボン パネルであるかどうかを示します (`FALSE`既定)。|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|アーカイブされたメニューを読み込みます。|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|ポップアップ メニュー バーを閉じるときの遅延のメニュー ボタンを復元します。|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|指定したインデックス位置には、ツール バー ボタンのスタイルを設定します。 (上書き[CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle))。|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|ポップアップ メニュー バーの行オフセットを設定します。|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|指定された遅延のポップアップ メニュー ボタンのタイマーを開始します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|アプリケーションが Windows XP の外観を持つ場合グレーのサイドバーが表示されるかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCPopupMenuBar`と同時に作成された、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)その内部に埋め込まれたとします。 `CMFCPopupMenuBar`の全体のクライアント領域を覆う、`CMFCPopupMenu`オブジェクトです。 キーボードとマウスの入力をサポートします。 入力とも通信、`CMFCPopupMenu`と最上位のフレーム ウィンドウにします。  
  
## <a name="example"></a>例  
 次の例では、初期化、`CMFCPopupMenuBar`オブジェクトから、`CMFCPopupMenu`オブジェクトです。 このコード スニペットの一部である、[クライアントの描画のサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&#7;](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpopupmenubar.h  
  
##  <a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 ポップアップ メニュー バーのウィンドウのレイアウトをすぐに再計算します。 (上書き[CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)します。  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bRecalcLayout`  
 `TRUE`ポップアップ メニュー バー ペインのレイアウトを自動的に再計算するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 指定されたメニュー リソースからのポップアップ メニュー項目を読み込みます。  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuResID`  
 読み込むメニュー リソースのメニュー ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`正常終了した場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 実行が遅れているポップアップ メニュー ボタンを閉じます。  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 ポップアップ メニュー ボタンのメニューを作成します。  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しいメニューにハンドルを返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 指定した点がどこにあるツールバーを検索します。  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 画面上のポイント。  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返しますツールバー ポイントにある therei が、いずれかの場合、または`NULL`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 メニュー ボタンのイメージのサイズを示します。  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールバーのメニュー ボタンのイメージのサイズを返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 既定のメニュー項目の識別子を返します。  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニュー バーで、既定のメニュー項目の識別子を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 最後に呼び出したのメニュー コマンドのインデックスを取得します。  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出された最後のメニュー コマンドのインデックスを返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 ポップアップ メニュー バーの行オフセットを取得します。  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニュー バーの行オフセットを返します。  
  
### <a name="remarks"></a>コメント  
 使用してこの値を設定[CMFCPopupMenuBar::SetOffset](#setoffset)します。  
  
##  <a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 指定されたメニューからのポップアップ メニュー ボタンをインポートします。  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
 ポップアップ メニュー ボタンのインポート元のメニュー。  
  
 [入力] `bShowAllCommands`  
 `TRUE`メニュー上のすべてのコマンドをインポートする場合、または`FALSE`使用頻度の低いものが表示されていない場合。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`メニュー ボタンのメニューから、正常にインポートされていない場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 ポップアップ メニュー バーがドロップ ダウン リスト モードであるかどうかを示します。  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`ポップアップ メニュー バーは、ドロップ ダウン リスト モードの場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 ポップアップ メニュー バーがパレット モードかどうかを示します。  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`パレット モードが有効になっている場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
 メニュー バーがパレット モードに設定されている場合は、複数の列と行の制限数にメニュー項目が表示されます。  
  
##  <a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 リボン パネルであるかどうかを示します (`FALSE`既定)。  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`FALSE`既定では、リボン パネルではないことを示します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 通常モードでリボン パネルであるかどうかを示します (`FALSE`既定)。  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`FALSE`既定ではないことを示すこのリボン パネル通常モードにします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 アーカイブされたメニューを読み込みます。  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
 読み込みにアーカイブされたメニューへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返します。 `TRUE` 、メニューが正常に読み込まれている場合、または`FALSE`かどうか。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Windows XP の外観があると、アプリケーションがグレーのサイドバーを持つかどうかを示すブール値パラメーターです。  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数に設定されている場合は、`FALSE`アプリケーションが Windows XP の外観と、アプリケーションでフレームワークがグレーのサイドバーを描画します。  
  
 既定値は `FALSE` です。  
  
##  <a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 ポップアップ メニュー バーを閉じるときの遅延のメニュー ボタンを復元します。  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 指定したインデックス位置には、ツール バー ボタンのスタイルを設定します。 (上書き[CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle))。  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 スタイルを設定するツール バー ボタンの&0; から始まるインデックス。  
  
 [入力] `nStyle`  
 ボタンのスタイル。 参照してください[ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)利用できるツール バー ボタンのスタイルの一覧です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 ポップアップ メニュー バーの行オフセットを設定します。  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iOffset`  
 ポップアップ メニュー バーをオフセットするか、行の数。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 指定された遅延のポップアップ メニュー ボタンのタイマーを開始します。  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuButton`  
 遅延タイマーを設定する対象のメニュー ボタンへのポインター。  
  
 [入力] `nDelayFactor`  
 遅延係数、標準のメニューの遅延時間 (0.5 秒の間で一般に、5 秒) に乗算する&1; 以上に等しい。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)

