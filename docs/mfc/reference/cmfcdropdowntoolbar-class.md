---
title: "CMFCDropDownToolBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar class
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
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
ms.openlocfilehash: ba643d67b12ba22bcf9fb54d32f3c329fa2c65a0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar クラス
ユーザーがトップレベルのツール バー ボタンを押し続けたときに表示されるツール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(上書き[CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap))。|  
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(上書き[CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar))。|  
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||  
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||  
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand` をオーバーライドします)。|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(上書き[CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/571a38ab-2a56-4968-9796-273516126f80))。|  
  
### <a name="remarks"></a>コメント  
 A`CMFCDropDownToolBar`オブジェクトは、ポップアップ メニューの動作と、ツールバーの外観を結合します。 ユーザーが押したおよびのボックスの一覧のツール バー ボタン (を参照してください[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md))、ドロップダウン ツールバーが表示され、ユーザーはそれにスクロールし、マウス ボタンを放すによってドロップダウン ツールバーから、ボタンを選択することができます。 ユーザーがドロップダウン ツールバーのボタンを選択すると、そのボタンが最上位レベルのツールバーの [現在] として表示されます。  
  
 ドロップダウン ツールバーをカスタマイズまたは、ドッキングされていることはできませんし、ティアオフ状態はありません。  
  
 次の図は、`CMFCDropDownToolBar`オブジェクト。  
  
 ![CMFCDropDownToolbar の](../../mfc/reference/media/cmfcdropdown.png "cmfcdropdown")  
  
 作成する、`CMFCDropDownToolBar`オブジェクトの通常のツールバーの作成と同じ方法 (を参照してください[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md))。  
  
 親ツールバー ドロップダウン ツールバーを挿入します。  
  
 1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
 2. 作成、`CMFCDropDownToolBarButton`ドロップダウン ツールバーを格納しているオブジェクト (詳細については、次を参照してください。 [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton))。  
  
 3. ダミー ボタンに置き換える、`CMFCDropDownToolBarButton`オブジェクトを使用して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。  
  
 ツール バー ボタンの詳細については、次を参照してください。[チュートリアル: ツールバーにコントロールを配置する](../../mfc/walkthrough-putting-controls-on-toolbars.md)です。 ドロップダウン ツールバーの例は、サンプル プロジェクト VisualStudioDemo を参照してください。  
  
## <a name="example"></a>例  
 次の例では、使用して、`Create`メソッドで、`CMFCDropDownToolBar`クラスです。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&29;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&30;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdropdowntoolbar.h  
  
##  <a name="a-nameallowshowonpanemenua--cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCDropDownToolBar::AllowShowOnPaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameloadbitmapa--cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>CMFCDropDownToolBar::LoadBitmap  
 アプリケーション リソースからツール バー イメージを読み込みます。  
  
```  
virtual BOOL LoadBitmap(
    UINT uiResID,  
    UINT uiColdResID=0,  
    UINT uiMenuResID=0,  
    BOOL bLocked=FALSE,  
    UINT uiDisabledResID=0,  
    UINT uiMenuDisabledResID=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiResID`  
 ツール バーのホット イメージを参照するビットマップのリソース ID。  
  
 [入力] `uiColdResID`  
 ツール バーのコールド イメージを参照するビットマップのリソース ID。  
  
 [入力] `uiMenuResID`  
 ツール バーの通常のメニュー イメージを参照するビットマップのリソース ID。  
  
 [入力] `bLocked`  
 `TRUE`ツールバーをロックするにはそれ以外の場合`FALSE`します。  
  
 [入力] `uiDisabledResID`  
 ツール バーの無効イメージを参照するビットマップのリソース ID。  
  
 [入力] `uiMenuDisabledResID`  
 メニューの無効イメージを参照するビットマップのリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex)メソッドは、ツールバーに関連付けられているイメージを読み込むには、このメソッドを呼び出します。 このメソッドをオーバーライドして、イメージ リソースのカスタムの読み込みを実行します。  
  
 ツール バーの作成後に、 `LoadBitmapEx` メソッドを呼び出して追加のイメージを読み込みます。  
  
##  <a name="a-nameloadtoolbara--cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CMFCDropDownToolBar::LoadToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadToolBar(
    UINT uiResID,  
    UINT uiColdResID = 0,  
    UINT uiMenuResID = 0,
    BOOL = FALSE,  
    UINT uiDisabledResID = 0,  
    UINT uiMenuDisabledResID = 0,  
    UINT uiHotResID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiResID`  
 [入力] `uiColdResID`  
 [入力] `uiMenuResID`  
 [入力] `BOOL`  
 [入力] `uiDisabledResID`  
 [入力] `uiMenuDisabledResID`  
 [入力] `uiHotResID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonlbuttonupa--cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>CMFCDropDownToolBar::OnLButtonUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 [入力] `point`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonmousemovea--cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>CMFCDropDownToolBar::OnMouseMove  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 [入力] `point`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsendcommanda--cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>CMFCDropDownToolBar::OnSendCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdatecmduia--cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCDropDownToolBar::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTarget`  
 [入力] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [チュートリアル: ツールバーへのコントロールを配置します。](../../mfc/walkthrough-putting-controls-on-toolbars.md)




