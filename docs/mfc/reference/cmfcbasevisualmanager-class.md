---
title: "CMFCBaseVisualManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- ~CMFCBaseVisualManager destructor
- CMFCBaseVisualManager class, destructor
- CMFCBaseVisualManager class
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c726fe71b7dcf26353fe0ce3a6b383eb5b578b9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager クラス
派生のビジュアル マネージャーと Windows テーマ API の間のレイヤー。  
  
 `CMFCBaseVisualManager`UxTheme.dll、利用可能であればを読み込んで Windows テーマ API メソッドへのアクセスを管理します。  
  
 このクラスは内部でのみ使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` オブジェクトを構築して初期化します。|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|現在の Windows テーマを使用してコンボ ボックスの枠線を描画します。|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|現在の Windows テーマを使用してコンボ ボックスのドロップダウン ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|現在の Windows テーマを使用して、プッシュ ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|現在の Windows テーマを使用して、オプション ボタン コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|進行状況バーをステータス バー コントロールの描画 ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|現在の Windows テーマを使用して、rebar コントロールの背景を設定します。|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|現在の Windows テーマを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`です。|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|呼び出し`OpenThemeData`をさまざまなコントロールを描画するためのハンドルを取得する: ウィンドウ、ツールバー、ボタン、およびなどです。|  
  
## <a name="remarks"></a>コメント  
 このクラスのオブジェクトを直接インスタンス化する必要はありません。  
  
 すべてのビジュアル マネージャーの基本クラスであるために呼び出すだけで済みます[CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)現在 Visual Manager へのポインターを取得しのメソッドにアクセスする、`CMFCBaseVisualManager`そのポインターを使用します。 ただし、現在の Windows テーマを使用して、コントロールを表示していれば勧めを使用する、`CMFCVisualManagerWindows`インターフェイスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>CMFCBaseVisualManager::CleanUpThemes  
 呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`です。  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>コメント  
 内部使用のみ。  
  
##  <a name="cmfcbasevisualmanager"></a>CMFCBaseVisualManager::CMFCBaseVisualManager  
 `CMFCBaseVisualManager` オブジェクトを構築して初期化します。  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>CMFCBaseVisualManager::DrawCheckBox  
 現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター  
  
 [入力] `rect`  
 チェック ボックスの外接する四角形。  
  
 [入力] `bHighlighted`  
 チェック ボックスが強調表示されているかどうかを指定します。  
  
 [入力] `nState`  
 0、オンで通常の場合はオフの場合、1 の  
  
 混合で通常の&2; になります。  
  
 [入力] `bEnabled`  
 チェック ボックスがオンになっているかどうかを指定します。  
  
 [入力] `bPressed`  
 チェック ボックスが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 値`nState`次のチェック ボックスのスタイルに対応します。  
  
|%n 状態|チェック ボックスのスタイル|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>CMFCBaseVisualManager::DrawComboBorder  
 現在の Windows テーマを使用してコンボ ボックスの枠線を描画します。  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 コンボ ボックスの枠線の外接する四角形。  
  
 [入力] `bDisabled`  
 コンボ ボックスの枠線が無効になっているかどうかを指定します。  
  
 [入力] `bIsDropped`  
 コンボ ボックスの枠線がドロップダウンになっているかどうかを指定します。  
  
 [入力] `bIsHighlighted`  
 コンボ ボックスの枠線が強調表示されているかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="drawcombodropbutton"></a>CMFCBaseVisualManager::DrawComboDropButton  
 現在の Windows テーマを使用してコンボ ボックスのドロップダウン ボタンを描画します。  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pDC`|デバイス コンテキストへのポインター。|  
|[入力] `rect`|コンボ ボックスのドロップダウン ボタンの外接する四角形。|  
|[入力] `bDisabled`|コンボ ボックスのドロップダウン ボタンが無効になっているかどうかを指定します。|  
|[入力] `bIsDropped`|コンボ ボックスのドロップダウン ボタンのドロップダウンはされているかどうかを指定します。|  
|[入力] `bIsHighlighted`|コンボ ボックスのドロップダウン ボタンが強調表示されているかどうかを指定します。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="drawpushbutton"></a>CMFCBaseVisualManager::DrawPushButton  
 現在の Windows テーマを使用して、プッシュ ボタンを描画します。  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 プッシュ ボタンの外接する四角形。  
  
 [入力] `pButton`  
 ポインター、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)描画するオブジェクト。  
  
 [入力] `uiState`  
 無視されます。 状態から取得`pButton`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="drawradiobutton"></a>CMFCBaseVisualManager::DrawRadioButton  
 現在の Windows テーマを使用して、オプション ボタン コントロールを描画します。  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 オプション ボタンの外接する四角形。  
  
 [入力] `bHighlighted`  
 オプション ボタンが強調表示されているかどうかを指定します。  
  
 [入力] `bChecked`  
 オプション ボタンがオンになっているかどうかを指定します。  
  
 [入力] `bEnabled`  
 オプション ボタンが有効になっているかどうかを指定します。  
  
 [入力] `bPressed`  
 オプション ボタンが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="drawstatusbarprogress"></a>CMFCBaseVisualManager::DrawStatusBarProgress  
 ステータス バー コントロールの進行状況バーを描画 ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。  
  
```  
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,   
    CMFCStatusBar* pStatusBar,   
    CRect rectProgress,   
    int nProgressTotal,   
    int nProgressCurr,  
    COLORREF clrBar,   
    COLORREF clrProgressBarDest,   
    COLORREF clrProgressText,   
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pStatusBar`  
 ステータス バーへのポインター。 この値は無視されます。  
  
 [入力] `rectProgress`  
 進行状況バーの外接する四角形`pDC`座標。  
  
 [入力] `nProgressTotal`  
 全体の進行状況の値です。  
  
 [入力] `nProgressCurr`  
 現在の進行状況の値。  
  
 [入力] `clrBar`  
 最初の色。 `CMFCBaseVisualManager`これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [入力] `clrProgressBarDest`  
 最後の色。 `CMFCBaseVisualManager`これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [入力] `clrProgressText`  
 進行状況のテキストの色。 `CMFCBaseVisualManager`これは無視されます。 テキストの色は`afxGlobalData.clrBtnText`です。  
  
 [入力] `bProgressText`  
 進行状況のテキストを表示するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="fillrebarpane"></a>CMFCBaseVisualManager::FillReBarPane  
 現在の Windows テーマを使用して、rebar コントロールの背景を設定します。  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pBar`  
 背景を描画するウィンドウへのポインター。  
  
 [入力] `rectClient`  
 塗りつぶす領域に外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`テーマの API は、有効な場合それ以外の場合`FALSE`します。  
  
##  <a name="getstandardwindowstheme"></a>CMFCBaseVisualManager::GetStandardWindowsTheme  
 現在の Windows テーマを取得します。  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されている Windows のテーマの色。 次の列挙値のいずれかを指定できます。  
  
- `WinXpTheme_None`-有効になっているテーマはありません。  
  
- `WinXpTheme_NonStandard`-(つまり、次の一覧から [なし] が、テーマが選択されている) 非標準のテーマを選択します。  
  
- `WinXpTheme_Blue`-青のテーマ (Luna)。  
  
- `WinXpTheme_Olive`-オリーブ テーマです。  
  
- `WinXpTheme_Silver`-銀色のテーマです。  
  
##  <a name="updatesystemcolors"></a>CMFCBaseVisualManager::UpdateSystemColors  
 呼び出し`OpenThemeData`をさまざまなコントロールを描画するためのハンドルを取得する: ウィンドウ、ツールバー、ボタン、およびなどです。  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>コメント  
 内部使用のみ。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

