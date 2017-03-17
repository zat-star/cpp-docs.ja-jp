---
title: "CStatusBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- indicators, status bar
- CStatusBar class
- status bars
- indicators
- status indicators
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e96070041ef5bcee0865991a14b6484082d8fc91
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbar-class"></a>CStatusBar クラス
テキスト出力用のペインまたは "インジケーター" の行を持つコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|`CStatusBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|指定したインジケーターの ID のインデックスを取得します。|  
|[CStatusBar::Create](#create)|ステータス バーを作成し、それをアタッチ、`CStatusBar`オブジェクト、および初期のフォントとバーの高さを設定します。|  
|[CStatusBar::CreateEx](#createex)|作成、 `CStatusBar` embedded 用の他のスタイルを使用してオブジェクト`CStatusBarCtrl`オブジェクトです。|  
|[CStatusBar::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分と呼び出されます。|  
|[CStatusBar::GetItemID](#getitemid)|指定されたインデックスのインジケーターの ID を取得します。|  
|[CStatusBar::GetItemRect](#getitemrect)|取得には、指定されたインデックスの四角形が表示されます。|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|指定されたインデックスのインジケーター ID、スタイル、および幅を取得します。|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|指定されたインデックスのインジケーターのスタイルを取得します。|  
|[CStatusBar::GetPaneText](#getpanetext)|指定されたインデックスのインジケーターのテキストを取得します。|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
|[CStatusBar::SetIndicators](#setindicators)|インジケーターの Id を設定します。|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|インジケーターの ID、スタイル、および指定されたインデックスの幅を設定します。|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|指定されたインデックスのインジケーターのスタイルを設定します。|  
|[CStatusBar::SetPaneText](#setpanetext)|指定されたインデックスのインジケーターのテキストを設定します。|  
  
## <a name="remarks"></a>コメント  
 出力ペイン一般的な用途はメッセージ行およびインジケーターとして使用します。 例には、選択されたメニュー コマンドを簡単に説明するメニュー ヘルプ メッセージ行と SCROLL LOCK、NUM LOCK、およびその他のキーのステータスを示すインジケーターが含まれます。  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)、メンバー関数は、新しい MFC 4.0 にすることができますステータス バーのカスタマイズなどの追加機能の Windows コモン コントロールのサポートを活用します。 `CStatusBar`メンバー関数は、Windows のコモン コントロール; の機能のほとんどを提供します。ただし、呼び出す`GetStatusBarCtrl`、さらに多くの Windows 95/98 ステータス バーの特性のステータス バーを与えることができます。 呼び出すと`GetStatusBarCtrl`への参照を返すには、`CStatusBarCtrl`オブジェクトです。 参照してください[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 フレームワークでは、左端の位置は 0 インジケーターを持つ配列のインジケーターの情報を格納します。 ステータス バーを作成する場合は、文字列、フレームワークが、対応するインジケーターを関連付けられる Id の配列を使用します。 文字列 ID またはインデックスのいずれかを使用して、インジケーターにアクセスすることができます。  
  
 既定では、最初のインジケーターは"elastic": 実行されると、その他のウィンドウが右揃えされるため、他のインジケーター ペインで使用されていないステータス バーの長さをします。  
  
 ステータス バーを作成するには、次の手順を実行します。  
  
1.  構築、`CStatusBar`オブジェクトです。  
  
2.  呼び出す、[作成](#create)(または[CreateEx](#createex)) ステータス バーのウィンドウを作成し、アタッチして、関数、`CStatusBar`オブジェクトです。  
  
3.  呼び出す[SetIndicators](#setindicators)に関連付ける各インジケーターの文字列 ID です。  
  
 ステータス バー ペインのテキストを更新する&3; つの方法があります。  
  
1.  呼び出す[とき](../../mfc/reference/cwnd-class.md#setwindowtext)ペイン 0 のみのテキストを更新します。  
  
2.  呼び出す[CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext)ステータス バーの `ON_UPDATE_COMMAND_UI`ハンドラー。  
  
3.  呼び出す[SetPaneText](#setpanetext)ペインのテキストを更新します。  
  
 呼び出す[SetPaneStyle](#setpanestyle)ステータス バー ペインのスタイルを更新します。  
  
 使用する方法について`CStatusBar`、記事を参照して[MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 指定された ID のインジケーターのインデックスを取得します。  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFind`  
 文字列のインデックスを取得するインジケーターの ID です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、インジケーターのインデックス以外の場合 –&1; です。  
  
### <a name="remarks"></a>コメント  
 最初のインジケーターのインデックスは 0 です。  
  
##  <a name="create"></a>CStatusBar::Create  
 ステータス バー (子ウィンドウ) を作成し、関連付けます、`CStatusBar`オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ウィンドウのステータス バーの親オブジェクトです。  
  
 `dwStyle`  
 ステータス バーのスタイル。 標準の Windows だけでなく[スタイル](../../mfc/reference/window-styles.md)、これらのスタイルがサポートされています。  
  
- `CBRS_TOP`コントロール バーは、フレーム ウィンドウの上部には。  
  
- `CBRS_BOTTOM`コントロール バーでは、フレーム ウィンドウの下部にあります。  
  
- `CBRS_NOALIGN`コントロール バーは、親のサイズが変更されたときに再配置されません。  
  
 `nID`  
 ツールバーの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 初期のフォントを設定し、状態を設定もバーの高さを既定値です。  
  
##  <a name="createex"></a>CStatusBar::CreateEx  
 ステータス バー (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CStatusBar`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ウィンドウのステータス バーの親オブジェクトです。  
  
 `dwCtrlStyle`  
 埋め込みを作成するための追加のスタイル[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクトです。 既定値を指定せず、サイズ変更グリップまたはツールヒントのステータス バーをサポートします。 ステータス バーのスタイルがサポートされている次のとおりです。  
  
- **SBARS_SIZEGRIP**ステータス バー コントロールには、ステータス バーの右端にあるサイズ変更グリップが含まれています。 サイズ変更グリップがサイズ変更境界線; に似ています。これは、ユーザーをクリックして、親ウィンドウのサイズを変更するドラッグ四角形の領域です。  
  
- ****ステータス バーがツール ヒントをサポートします。  
  
 これらのスタイルの詳細については、「 [CStatusBarCtrl の設定](../../mfc/settings-for-the-cstatusbarctrl.md)します。  
  
 `dwStyle`  
 ステータス バーのスタイル。 既定値は、フレーム ウィンドウの下部にあるステータス バーが表示を作成することを指定します。 ステータス バーに示されているコントロールのスタイルの任意の組み合わせを適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)と[CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create)します。 ただし、このパラメーターは、WS_CHILD と WS_VISIBLE のスタイルを常に含める必要があります。  
  
 `nID`  
 子ウィンドウのステータス バーの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数も初期のフォントを設定し、設定、ステータス バーの高さを既定値です。  
  
 使用`CreateEx`の代わりに[作成](#create)、特定のスタイルが埋め込まれたステータス バー コントロールの作成時に存在する必要がある場合。 たとえば、設定`dwCtrlStyle`に**には**ステータス バー オブジェクトにツールヒントを表示します。  
  
##  <a name="cstatusbar"></a>CStatusBar::CStatusBar  
 構築、`CStatusBar`オブジェクトは、必要に応じて、既定のステータス バーのフォントを作成し、フォントの特性を既定値に設定します。  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>CStatusBar::DrawItem  
 このメンバー関数は、オーナー描画ステータス バーの変更のビジュアルな部分と、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 オーナー描画の描画を実装するには、この関数をオーバーライド`CStatusBar`オブジェクトです。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`このメンバー関数が終了する前にします。  
  
##  <a name="getitemid"></a>CStatusBar::GetItemID  
 指定したインジケーターの ID を返す`nIndex`します。  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 ID を取得するインジケーターのインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインジケーターの ID`nIndex`します。  
  
##  <a name="getitemrect"></a>CStatusBar::GetItemRect  
 指定したインジケーターの座標をコピー`nIndex`が指す構造体に`lpRect`します。  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 四角形の座標インジケーターのインデックスでは、取得します。  
  
 `lpRect`  
 指す、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトで指定したインジケーターの座標を受け取る`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 座標は、ステータス バーの左上隅に対して相対的 (ピクセル単位)。  
  
##  <a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 セット`nID`、 `nStyle`、および`cxWidth`ID、スタイル、およびによって指定された位置にインジケーター ウィンドウの幅を`nIndex`します。  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 その情報を取得するペインのインデックス。  
  
 `nID`  
 参照、 **UINT**ペインの ID に設定されています。  
  
 `nStyle`  
 参照、 **UINT**ウィンドウのスタイルに設定されています。  
  
 `cxWidth`  
 ウィンドウの幅に設定されている整数への参照。  
  
##  <a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 ステータス バーのウィンドウのスタイルを取得するには、このメンバー関数を呼び出します。  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 スタイルを取得するペインのインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したステータス バー ペインのスタイル`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのスタイルでは、ペインの表示方法を決定します。  
  
 ステータス バーで使用可能なスタイルの一覧は、次を参照してください。[作成](#create)します。  
  
##  <a name="getpanetext"></a>CStatusBar::GetPaneText  
 ステータス バー ペインに表示されるテキストを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  ```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be retrieved.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that contains the text to be retrieved.  
  
### Return Value  
 A `CString` object containing the pane's text.  
  
### Remarks  
 The second form of this member function fills a `CString` object with the string text.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 This member function allows direct access to the underlying common control.  
  
```  
Const; CStatusBarCtrl >/documents/report1.rdl」の GetStatusBarCtrl()  
```  
  
### Return Value  
 Contains a reference to a [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) object.  
  
### Remarks  
 Use `GetStatusBarCtrl` to take advantage of the functionality of the Windows status-bar common control, and to take advantage of the support [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) provides for status-bar customization. For example, by using the common control, you can specify a style that includes a sizing grip on the status bar, or you can specify a style to have the status bar appear at the top of the parent window's client area.  
  
 For more general information about common controls, See [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Sets each indicator's ID to the value specified by the corresponding element of the array `lpIDArray`, loads the string resource specified by each ID, and sets the indicator's text to the string.  
  
```  
BOOL SetIndicators (lpIDArray UINT * const、  
    int nIDCount) です。
```  
  
### Parameters  
 `lpIDArray`  
 Pointer to an array of IDs.  
  
 `nIDCount`  
 Number of elements in the array pointed to by `lpIDArray`.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Sets the specified indicator pane to a new ID, style, and width.  
  
```  
void SetPaneInfo (int nIndex、  
    UINT では、  
    UINT それぞれ  
    int cxWidth) です。
```  
  
### Parameters  
 `nIndex`  
 Index of the indicator pane whose style is to be set.  
  
 `nID`  
 New ID for the indicator pane.  
  
 `nStyle`  
 New style for the indicator pane.  
  
 `cxWidth`  
 New width for the indicator pane.  
  
### Remarks  
 The following indicator styles are supported:  
  
- **SBPS_NOBORDERS** No 3-D border around the pane.  
  
- **SBPS_POPOUT** Reverse border so that text "pops out."  
  
- **SBPS_DISABLED** Do not draw text.  
  
- **SBPS_STRETCH** Stretch pane to fill unused space. Only one pane per status bar can have this style.  
  
- **SBPS_NORMAL** No stretch, borders, or pop-out.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Call this member function to set the style of a status bar's pane.  
  
```  
void SetPaneStyle (int nIndex、  
    UINT nStyle) です。
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose style is to be set.  
  
 `nStyle`  
 Style of the pane whose style is to be set.  
  
### Remarks  
 A pane's style determines how the pane appears.  
  
 For a list of styles available for status bars, see [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Call this member function to set the pane text to the string pointed to by `lpszNewText`.  
  
```  
BOOL SetPaneText (int nIndex、  
    LPCTSTR されています。  
    BOOL b 更新 = TRUE)。
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be set.  
  
 `lpszNewText`  
 Pointer to the new pane text.  
  
 *bUpdate*  
 If **TRUE**, the pane is invalidated after the text is set.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 After you call `SetPaneText`, you must add a UI update handler to display the new text in the status bar.  
  
### Example  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## See Also  
 [MFC Sample CTRLBARS](../../visual-cpp-samples.md)   
 [MFC Sample DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)

