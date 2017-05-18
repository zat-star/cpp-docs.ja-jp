---
title: "CTooltipManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager class
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
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
ms.openlocfilehash: 3bbf191aacdd318f2afb0bd1a126c3eff290fad6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipmanager-class"></a>CTooltipManager クラス
ツールヒントに関するランタイム情報を保持します。 `CTooltipManager` クラスのインスタンスは、アプリケーションごとに&1; 回作成されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|指定された Windows コントロールの種類のツールヒント コントロールを作成します。|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|ツールヒント コントロールを削除します。|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|指定された Windows コントロールの種類のツールヒント コントロールの外観をカスタマイズします。|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|ツールヒント コントロールのテキストと説明を設定します。|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>コメント  
 使用[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo`、および`CTooltipManager`アプリケーションでカスタマイズしたツール ヒントを実装するためにします。 これらのツール ヒント クラスを使用する方法の例は、次を参照してください。、 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)トピックです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Tooltip コントロールを作成します。  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pToolTip`  
 ツールヒントのポインターへの参照。 関数が返す場合は、新しく作成されたツールヒントをポイントに設定されます。  
  
 [入力] `pWndParent`  
 ツールヒントの親です。  
  
 [入力] `nType`  
 ツール ヒントの種類です。  
  
### <a name="return-value"></a>戻り値  
 ツール ヒントが正常に作成された場合は&0; 以外の値。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[CTooltipManager::DeleteToolTip](#deletetooltip)で戻されたツールヒント コントロールを削除する`pToolTip`です。  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)を作成する各ツールヒントの視覚的な表示パラメーターは、ツールヒントに基づくセットの種類を`nType`を指定します。 1 つまたは複数のツールヒント型のパラメーターを変更するには、呼び出す[CTooltipManager::SetTooltipParams](#settooltipparams)します。  
  
 有効なツールヒントの種類は、次の表のとおりです。  
  
|ツールヒントの種類|コントロールの分類|型の例|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|ボタンをクリックします。|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|キャプション バー。|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|別のカテゴリに一致しないコントロール。|なし。|  
|AFX_TOOLTIP_TYPE_DOCKBAR|ドッキング可能ペインです。|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|テキスト ボックスです。|なし。|  
|AFX_TOOLTIP_TYPE_MINIFRAME|ミニフレームします。|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|プランナー|なし。|  
|AFX_TOOLTIP_TYPE_RIBBON|リボン バーです。|CMFCRibbonBar CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|タブ コントロールです。|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|ツールバーです。|CMFCToolBar CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|ツールボックスです。|なし。|  
  
##  <a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 ツールヒント コントロールを削除します。  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pToolTip`  
 破棄するツールヒントへのポインターへの参照。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すごとに[CToolTipCtrl クラス](../../mfc/reference/ctooltipctrl-class.md)によって作成された[CTooltipManager::CreateToolTip](#createtooltip)します。 親コントロールからこのメソッドを呼び出す必要があります、`OnDestroy`ハンドラー。 これが正しく、framework からヒントを削除する必要です。 このメソッドは、設定`pToolTip`に`NULL`を返す前にします。  
  
##  <a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 指定した Windows コントロールの種類のツール ヒント コントロールの外観をカスタマイズします。  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTypes`  
 コントロールの種類を指定します。  
  
 [入力] `pRTC`  
 カスタム ツールヒントのランタイム クラスです。  
  
 [入力] `pParams`  
 ツール ヒントのパラメーターです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを設定、ランタイム クラスと初期パラメーターを[CToolTipManager](../../mfc/reference/ctooltipmanager-class.md)ツールヒントを作成するときに使用します。 コントロールを呼び出すと[CTooltipManager::CreateToolTip](#createtooltip)がツールヒントにパスとなる型で示された種類のいずれかと`nTypes`、ツールヒント マネージャーで指定されたランタイム クラスのインスタンスであるツールヒント コントロールを作成する`pRTC`で指定されたパラメーターを渡す`pParams`新しいツールヒントにします。  
  
 このメソッドを呼び出すと、既存のすべてのツールヒント所有者 AFX_WM_UPDATETOOLTIPS メッセージが表示されツールヒントを使用して再作成する必要があります[CTooltipManager::CreateToolTip](#createtooltip)します。  
  
 `nTypes`有効なツールヒントの任意の組み合わせの種類は、 [CTooltipManager::CreateToolTip](#createtooltip)で使用することもできます AFX_TOOLTIP_TYPE_ALL します。 AFX_TOOLTIP_TYPE_ALL を渡すと、すべてのツール ヒントの種類に影響します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`SetTooltipParams`のメソッド、`CTooltipManager`クラスです。 このコード スニペットの一部である、[クライアントの描画のサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&#11;](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 テキストとツールヒントの説明を設定します。  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTI`  
 TOOLINFO オブジェクトへのポインター。  
  
 [入力、出力] `pToolTip`  
 テキストと説明を設定するツール ヒント コントロールへのポインター。  
  
 [入力] `nType`  
 このツール ヒントが関連付けられているコントロールの種類を指定します。  
  
 [入力] `strText`  
 ツールヒントのテキストとして設定するテキストです。  
  
 [入力] `lpszDescr`  
 Tooltip の説明へのポインター。 できる`NULL`です。  
  
### <a name="remarks"></a>コメント  
 値`nType`と同じ値にする必要があります、`nType`のパラメーター [CTooltipManager::CreateToolTip](#createtooltip)ツールヒントを作成したときにします。  
  
##  <a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)

