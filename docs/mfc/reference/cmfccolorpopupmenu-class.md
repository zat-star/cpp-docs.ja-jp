---
title: "CMFCColorPopupMenu クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu class
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14076d78eaf86ef01e68656685dd2fd102d96311
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu クラス
ユーザーがドキュメントまたはアプリケーションに色の選択に使用するポップアップ メニューを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` オブジェクトを構築します。|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|ドッキング可能なティアオフ カラー バーを作成します。 (上書き[CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar))。|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|返します。、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 、ポップアップ メニュー内に埋め込まれています。 (上書き[CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar))。|  
|`CMFCColorPopupMenu::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|埋め込みのプロパティ グリッド コントロール オブジェクトを設定`CMFCColorBar`オブジェクトです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`m_bEnabledInCustomizeMode`|カラー バーを表示するかどうかを決定するブール値。|  
|`m_wndColorBar`|`CMFCColorBar`色の選択を提供するオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このクラスは継承のポップアップ メニュー機能、`CMFCPopupMenu`クラスし、管理、`CMFCColorBar`色の選択を提供するオブジェクト。 ツール バー フレームワークがカスタマイズ モードで、`m_bEnabledInCustomizeMode`に設定されているメンバー `FALSE`、カラー バー オブジェクトは表示されません。 カスタマイズ モードの詳細については、次を参照してください[CMFCToolBar::IsCustomizeMode。](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 詳細については`CMFCColorBar`を参照してください[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorpopupmenu.h  
  
##  <a name="a-namecmfccolorpopupmenua--cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu  
 `CMFCColorPopupMenu` オブジェクトを構築します。  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colors`  
 フレームワークは、ポップアップ メニューに表示する色の配列。  
  
 [入力] `color`  
 既定値は、色を選択します。  
  
 [入力] `lpszAutoColor`  
 テキスト ラベル、*自動*(既定) の色のボタン、または`NULL`です。  
  
 自動のボタンの標準のラベルは**自動**です。  
  
 [入力] `lpszOtherColor`  
 テキスト ラベル、*他の*ボタンを他の色を表示、または`NULL`です。  
  
 その他のボタンの標準のラベルは**他の色。**.  
  
 [入力] `lpszDocColors`  
 ドキュメントの色のボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントが現在使用されているすべての色が一覧表示します。  
  
 [入力] `lstDocColors`  
 ドキュメントが現在使用されている色の一覧。  
  
 [入力] `nColumns`  
 色の配列がある列の数。  
  
 [入力] `nHorzDockRows`  
 カラー バーが水平方向にドッキングされている行の数。  
  
 [入力] `nVertDockColumns`  
 カラー バーが垂直方向にドッキングされている列の数。  
  
 [入力] `colorAutomatic`  
 クリックすると、自動的に適用される既定の色。  
  
 [入力] `uiCommandID`  
 カラー バー コントロールのコマンド id。  
  
 [入力] `bStdColorDlg`  
 標準的なシステムの色 ダイアログ ボックスを表示するかどうかを示すブール値、または[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス。  
  
 [入力] `pParentBtn`  
 親ボタンへのポインター。  
  
 [入力] `nID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 それぞれのオーバー ロードされたコンス トラクターのセット、`m_bEnabledInCustomizeMode`メンバー`FALSE`します。  
  
### <a name="example"></a>例  
 次の例では、構築、`CMFCColorPopupMenu`オブジェクトです。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&34;](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="a-namecreatetearoffbara--cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar  
 ドッキング可能なティアオフ カラー バーを作成します。  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWndMain`|ティアオフ バーの親ウィンドウへのポインター。|  
|[入力] `uiID`|ティアオフ バーのコマンド ID。|  
|[入力] `lpszName`|ティアオフ バーのウィンドウのテキスト。|  
  
### <a name="return-value"></a>戻り値  
 新しいティアオフ コントロール バー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、作成、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトおよびにキャスト、 [CPane クラス](../../mfc/reference/cpane-class.md)ポインター。 この値をキャストすることに、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)で説明するキャスト マクロのいずれかを使用してポインター [MFC クラス オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)します。  
  
##  <a name="a-namegetmenubara--cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>CMFCColorPopupMenu::GetMenuBar  
 返します。、 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 、ポップアップ メニュー内に埋め込まれています。  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>戻り値  
 埋め込まれたへのポインター`CMFCPopupMenuBar`します。  
  
### <a name="remarks"></a>コメント  
 色のポップアップ メニューが、埋め込み[CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)オブジェクトです。 アプリケーションが別の埋め込み型を使用する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="a-namesetproplista--cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>CMFCColorPopupMenu::SetPropList  
 埋め込みのプロパティ グリッド コントロール オブジェクトを設定`CMFCColorBar`オブジェクトです。  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndList`  
 プロパティ グリッド コントロール オブジェクトへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

