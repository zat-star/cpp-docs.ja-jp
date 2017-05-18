---
title: "CMFCStatusBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar class
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 20881637d74bafffbcf2e0c3dcd1cc98e173aa07
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar クラス
`CMFCStatusBar`クラスに似たステータス バー、`CStatusBar`クラスです。 ただし、 `CMFCStatusBar` クラスには、イメージ、アニメーション、およびプログレス バーを表示する機能や、マウスのダブルクリックに応答する機能など、 `CStatusBar` クラスでは提供されない機能が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(上書き[CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|コントロール バーを作成し、それをアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクトです。 (上書き[CPane::Create](../../mfc/reference/cpane-class.md#create))。|  
|[CMFCStatusBar::CreateEx](#createex)|コントロール バーを作成し、それをアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクトです。 (上書き[CPane::CreateEx](../../mfc/reference/cpane-class.md#createex))。|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|このペインと親フレームの間の別のウィンドウを動的に挿入するかどうかを決定します。 (上書き[CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|有効または無効にマウスの処理がステータス バーをダブルクリックします。|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|指定したウィンドウで進行状況バーを表示します。|  
|[CMFCStatusBar::GetCount](#getcount)|ステータス バー ペインの数を返します。|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|ウィンドウ スタイルを返します。 (上書き[CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle))。|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|ステータス バーの指定したウィンドウのピクセル単位の幅を返します。|  
|[CMFCStatusBar::GetTipText](#gettiptext)|ステータス バーの指定したウィンドウのツールヒントのテキストを返します。|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|指定したウィンドウを無効にし、そのコンテンツを再描画します。|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|これに接続されている Windows のウィンドウの作成前に、フレームワークによって呼び出さ`CWnd`オブジェクトです。 (上書き[CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow))。|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|指定したウィンドウにアニメーションを割り当てます。|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|ステータス バーの指定したウィンドウの背景色を設定します。|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|ステータス バーの指定したウィンドウのインジケーター アイコンを設定します。|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|ステータス バーの指定したウィンドウで進行状況バーの現在の進行状況を設定します。|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|ウィンドウのスタイルを設定します。 (上書き[CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle))。|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|ステータス バーの指定したウィンドウのテキストの色を設定します。|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|ステータス バーの指定したウィンドウのピクセルの幅を設定します。|  
|[CMFCStatusBar::SetTipText](#settiptext)|ステータス バーの指定したウィンドウのツールヒントのテキストを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|ステータス バー ペインを再描画するときに、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 次の図は、図からのステータス バーの[ステータス バーのデモのサンプル](../../visual-cpp-samples.md)アプリケーションです。  
  
 ![CMFCStatusBar の例](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>例  
 次の例では、アプリケーションがさまざまなメソッドを呼び出すに使用するローカル変数、`CMFCStatusBar`クラスです。 これらの変数は、StatusBarDemoView.h で宣言されます。 メイン フレームが MainFrm.h で宣言されている、ドキュメントが StatusBarDemoDoc.h で宣言されているおよび StatusBarDemoView.h でビューが宣言されています。 このコード スニペットの一部である、[ステータス バーのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#9;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>例  
 次の例への参照を取得する方法を示します`CMFCStatusBar`オブジェクトを導入することにより、 `GetStatusBar` MainFrm.h およびからこのメソッドを呼び出すメソッド、 `GetStatusBar` StatusBarDemoView.h 内のメソッドです。 このコード スニペットの一部である、[ステータス バーのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#7;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#8;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドの呼び出しは、 `CMFCStatusBar` StatusBarDemoView.cpp 内のクラスです。 定数は、MainFrm.h で宣言されます。 この例では、アイコンの設定、ステータス バー ペインのツールヒント テキストを設定、指定したウィンドウに進行状況バーを表示、アニメーションを指定したウィンドウに割り当て、テキストとステータス バー ペインの幅を設定およびステータス バー ペインの進行状況バーの現在の進行状況インジケーターを設定する方法を示します。 このコード スニペットの一部である、[ステータス バーのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&6;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&4;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#5;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout  
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
  
##  <a name="commandtoindex"></a>CMFCStatusBar::CommandToIndex  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDFind`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>CMFCStatusBar::Create  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 [入力] `dwStyle`  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="createex"></a>CMFCStatusBar::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentWnd`  
 [入力] `dwCtrlStyle`  
 [入力] `dwStyle`  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick  
 有効または無効にマウスの処理がステータス バーをダブルクリックします。  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 場合`TRUE`、有効にする、マウスの処理 をダブルクリックします。 それ以外の場合、マウスのダブルクリックの処理を無効にします。  
  
### <a name="remarks"></a>コメント  
 Windows ステータス バーが二重のクリックを処理する有効な場合は送信、`WM_COMMAND`所有者にリソース ID と共にのステータス バーのステータス バー ペインのユーザーがダブルクリックするたびに通知します。  
  
##  <a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar  
 指定したウィンドウで進行状況バーを表示します。  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 有効にするには、その進行状況バー ペインのインデックスを指定します。  
  
 [入力] `nTotal`  
 進行状況バーの最大値を指定します。  
  
 [入力] `bDisplayText`  
 進行状況バーが現在の進行状況の値を表示するかどうかを指定します。  
  
 [入力] `clrBar`  
 進行状況バーの背景色を指定します。  
  
 [入力] `clrBarDest`  
 進行状況バーの背景の&2; 番目の色を指定します。 異なる値を使用して`clrBar`でグラデーションに適用される色を埋めるためです。  
  
 [入力] `clrProgressText`  
 進行状況バーのテキストの色を指定します。  
  
### <a name="remarks"></a>コメント  
 進行状況バーの呼び出しを無効にする場合は、`EnablePaneProgressBar`と`nTotal`-1 に設定します。 既定では`nTotal`は 100 に設定します。 そのため、進行状況をパーセンテージとして表示する追加の計算は必要ありません。  
  
 別の値を渡す必要があります`clrBar`と`clrBarDest`進行状況バーの背景色がグラデーションに適用される色が表示されるようにします。 をクリックします。  
  
 現在の進行状況を設定する、 [CMFCStatusBar::SetPaneProgress](#setpaneprogress)メソッドです。  
  
##  <a name="getcount"></a>CMFCStatusBar::GetCount  
 ステータス バーに含まれるウィンドウの数を取得します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ペインの数。  
  
##  <a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getitemid"></a>CMFCStatusBar::GetItemID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getitemrect"></a>CMFCStatusBar::GetItemRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `lpRect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `nID`  
 [入力] `nStyle`  
 [入力] `cxWidth`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanetext"></a>CMFCStatusBar::GetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `s`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth  
 ステータス バーのウィンドウの幅を取得します。  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 ステータス バー ペインのインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ペインの幅を`nIndex`を指定します。 それ以外の場合、ステータス バー ペインが存在しない場合は&0; です。  
  
##  <a name="gettiptext"></a>CMFCStatusBar::GetTipText  
 ステータス バーのウィンドウのツールヒント テキストを取得します。  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 ツールヒントのテキストを取得する対象のウィンドウのインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ペインのツールヒント テキストを`nIndex`を指定します。 空の文字列は、指定されたステータス バー ペインが存在しない場合、それ以外の場合`nIndex`かそのツールヒント テキストが空です。  
  
##  <a name="invalidatepanecontent"></a>CMFCStatusBar::InvalidatePaneContent  
 ステータス バー ペインを無効化し、そのコンテンツを再描画します。  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 無効化され、再描画するがコンテンツを持つペインのインデックスを指定します。  
  
### <a name="remarks"></a>コメント  
 ステータス バーを無効にすると、再描画にマークされます。 Windows が再描画時に、`UpdateWindow`メソッドの送信、`WM_PAINT`メッセージを`OnPaint`メソッドです。  
  
##  <a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane  
 ステータス バーのウィンドウを再描画します。  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 描画のためのデバイス コンテキストへのポインター。  
  
 [入力] `pPane`  
 ポインター、`CMFCStatusBarPaneInfo`を再描画するのには、ウィンドウに関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、`OnDrawPane`デバイス コンテキストを使用して、ウィンドウを再描画`pDC`ペインのスタイルおよびコンテンツに従ってします。  
  
 このメソッドをオーバーライドして、 `CMFCStatusBar`-ウィンドウの外観をカスタマイズするクラスを派生します。  
  
##  <a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `cs`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setindicators"></a>CMFCStatusBar::SetIndicators  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpIDArray`  
 [入力] `nIDCount`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation  
 指定したウィンドウにアニメーションを割り当てます。  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 アニメーションを割り当てるペインのインデックスを指定します。  
  
 [入力] `hImageList`  
 アニメーション フレームを保持しているイメージ一覧へのハンドルを指定します。  
  
 [入力] `nFrameRate`  
 アニメーションのミリ秒単位で、フレーム レートを指定します。  
  
 [入力] `bUpdate`  
 場合`TRUE`ペインのコンテンツをすぐに更新します。 それ以外の場合は無効になる、ペインのコンテンツが更新されます。  
  
### <a name="remarks"></a>コメント  
 現在のアニメーションを無効にする場合は、呼び出す`SetPaneAnimation`と`hImageList`に設定`NULL`します。  
  
##  <a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor  
 ステータス バー ペインの背景色を設定します。  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 新しい背景色を設定する対象のウィンドウのインデックスを指定します。  
  
 [入力] `clrBackground`  
 新しい背景色を指定します。  
  
 [入力] `bUpdate`  
 場合`TRUE`ペインのコンテンツをすぐに更新します。 それ以外の場合は更新されません ウィンドウの内容まで、別の方法で、ウィンドウが無効になりません。  
  
##  <a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon  
 ステータス バー ペインのアイコンを設定します。  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 イメージを設定する対象のウィンドウのインデックスを指定します。  
  
 [入力] `hIcon`  
 ウィンドウの画像として設定するアイコンを識別するハンドルを指定します。  
  
 [入力] `bUpdate`  
 ペインのコンテンツをすぐに更新するかどうかを指定します。  
  
 [入力] `hBmp`  
 ウィンドウの画像として設定するビットマップを識別するハンドルを指定します。  
  
 [入力] `clrTransparent`  
 ビットマップの透明色を指定する、`hBmp`を示します。  
  
### <a name="remarks"></a>コメント  
 いずれかを渡すことができます`HICON`または`HBITMAP`と共にウィンドウのイメージを設定する透明色。 できなくなった場合、イメージを表示したくない場合、`NULL`イメージ ハンドルとして値。  
  
 すべての実行中のアニメーションがある場合を[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)が設定すると、アニメーションは停止されます。  
  
##  <a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `nID`  
 [入力] `nStyle`  
 [入力] `cxWidth`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress  
 指定したウィンドウで進行状況バーの現在の進行状況インジケーターを設定します。  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 進行状況インジケーターを更新するペインのインデックスを指定します。  
  
 [入力] `nCurr`  
 進行状況インジケーターの現在の値を指定します。  
  
 [入力] `bUpdate`  
 ウィンドウを直ちに更新かどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 指定したウィンドウで進行状況バーの進行状況インジケーターを更新するときに、このメソッドを呼び出します。  
  
 指定したウィンドウでこの関数を使用するを呼び出す必要があります[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)最初です。  
  
##  <a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `nStyle`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanetext"></a>CMFCStatusBar::SetPaneText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 [入力] `lpszNewText`  
 [入力] `bUpdate`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor  
 指定したウィンドウのテキストの色を設定します。  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 新しいテキストの色を割り当てるペインのインデックスを指定します。  
  
 [入力] `clrText`  
 テキストの色を指定します。  
  
 [入力] `bUpdate`  
 場合`TRUE`ペインのコンテンツをすぐに更新します。 それ以外の場合は更新されません ウィンドウの内容まで、別の方法で、ウィンドウが無効になりません。  
  
##  <a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth  
 ステータス バー ペインの幅を設定します。  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 新しい幅を設定する対象のステータス バー ペインのインデックス。  
  
 [入力] `cx`  
 ステータス バー ペインのピクセル単位での新しい幅。  
  
##  <a name="settiptext"></a>CMFCStatusBar::SetTipText  
 ステータス バー ペインのツールヒント テキストを設定します。  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 ツールヒント テキストを割り当てるペインのインデックス。  
  
 [入力] `pszTipText`  
 新しいツールヒント テキスト。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)

