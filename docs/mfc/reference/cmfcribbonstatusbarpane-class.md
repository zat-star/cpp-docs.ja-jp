---
title: "CMFCRibbonStatusBarPane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane クラス
`CMFCRibbonStatusBarPane`クラスは、リボン ステータス バーに追加できるリボン要素を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|切り捨てることがなくペインに表示できる最大長の文字列を定義する文字列を返します。|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|テキストの配置の現在の設定を返します。|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|アニメーションが進行中かどうかを決定します。|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|リボン ステータス バーの拡張領域内のウィンドウがあるかどうかを決定します。|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(上書き[CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder))。|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(上書き[CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground))。|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|切り捨てることがなくペインに表示できる最大長の文字列を定義します。|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|ウィンドウに、アニメーションを使用できるイメージ リストを割り当てます。|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|テキストの配置を設定します。|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|ウィンドウに割り当てられているアニメーションを開始します。|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|ウィンドウに割り当てられているアニメーションを停止します。 」を参照してください。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|ウィンドウに割り当てられているアニメーションが停止したときに、フレームワークによって呼び出されます。|  
  
## <a name="example"></a>例  
 次の例は、`CMFCRibbonStatusBarPane` クラスのさまざまなメソッドの使用方法を説明しています。 例では、作成する方法を示しています、`CMFCRibbonStatusBarPane`オブジェクト、ステータス バー ペインのラベルのテキストの配置設定、切り捨てることがなく、ステータス バー ペインに表示できる、ステータス バー ペインに、アニメーションを使用でき、アニメーションを開始するイメージ リストをアタッチする時間が最も長いテキストを定義します。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 ステータス バー ペインのオブジェクトを構築します。  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nCmdID`  
 ウィンドウのコマンド ID を指定します。  
  
 [入力] `lpszText`  
 ウィンドウに表示するテキスト文字列を指定します。  
  
 [入力] `bIsStatic`  
 場合`TRUE`、ステータス ウィンドウの強調表示されているまたはをクリックして選択されていることはできません。  
  
 [入力] `hIcon`  
 ウィンドウに表示されるアイコンのハンドルを指定します。  
  
 [入力] `lpszAlmostLargeText`  
 ウィンドウが表示可能な最大長の文字列を指定します。  
  
 [入力] `hBmpAnimationList`  
 アニメーションで使用されるイメージ リストへのハンドルを指定します。  
  
 [入力] `cxAnimation`  
 アニメーションで使用されるイメージ リストのアイコンのピクセル単位の幅を指定します。  
  
 [入力] `clrTrnsp`  
 アニメーションで使用されるイメージ リストのイメージの透明色を指定します。  
  
 [入力] `uiAnimationListResID`  
 アニメーションで使用されるイメージ リストのリソース ID を指定します。  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 ステータス バー ペインを表示できる最大長の文字列を取得します。  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ペインに表示できる最も長いテキスト文字列。  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 ステータス バー ペインのラベルのテキストの配置の現在の設定を取得します。  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかに現在のテキスト配置します。  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT します。  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 アニメーションが進行中かどうかを決定します。  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アニメーションが実行中の場合`FALSE`それ以外の場合。  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 リボン ステータス バーの拡張領域内のウィンドウがあるかどうかを確認します。  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウがステータス バーの拡張領域にある場合は。 それ以外の場合は `FALSE`。  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CDC*`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 フレームワークは、ウィンドウに割り当てられているアニメーションが終了すると、このメソッドを呼び出します。  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>コメント  
 `StopAnimation`メソッドの呼び出し、`OnFinishAnimation`メソッドで、アニメーションが終了すると、データのクリーンアップを行うこともできます。  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 切り捨てることがなく、ステータス バー ペインに表示できる最も長いテキストを定義します。  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszAlmostLargeText`  
 切り捨てることがなく、ステータス バー ペインに表示できる最大長の文字列を指定します。  
  
### <a name="remarks"></a>コメント  
 ライブラリは、テキストのサイズを計算する`lpszAlmostLargeText`を指定し、それに応じて、ウィンドウのサイズを変更します。 ウィンドウにも適合しない場合は、テキストが切り捨てられます。  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 ステータス バー ペインに、アニメーションを使用できるイメージ リストをアタッチします。  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hBmpAnimationList`  
 イメージ リストへのハンドルを指定します。  
  
 [入力] `cxAnimation`  
 イメージ リスト内のフレームのピクセル単位の幅を指定します。  
  
 [入力] `clrTransp`  
 イメージ リストの透明色を指定します。  
  
 [入力] `uiAnimationListResID`  
 イメージ リストのリソース ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`イメージ リストが、ステータス バー ペインに正常に接続されている場合`FALSE`それ以外の場合。  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 ステータス バー ペインのラベルのテキストの配置を設定します。  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nAlign`  
 テキストの配置を指定します。  
  
### <a name="remarks"></a>コメント  
 `nAlign`次の値のいずれかを設定できます。  
  
- `TA_LEFT`: 左寄せ  
  
- `TA_CENTER:`中央揃え  
  
- `TA_RIGHT:`右揃え  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 ウィンドウに割り当てられるアニメーションを開始します。  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFrameDelay`  
 アニメーションのフレーム レートをミリ秒単位で指定します。  
  
 [入力] `nDuration`  
 ミリ秒単位で、アニメーションを再生する期間を指定します。 無限ループに-1 を使用します。  
  
### <a name="remarks"></a>コメント  
 呼び出す前に、イメージ リストへのハンドルを指定する必要があります`StartAnimation`を使用して`SetAnimationList`します。  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 ステータス バー ペインに割り当てられているアニメーションを停止します。  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar クラス](../../mfc/reference/cmfcribbonstatusbar-class.md)

