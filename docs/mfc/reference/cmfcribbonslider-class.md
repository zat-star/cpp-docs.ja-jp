---
title: "CMFCRibbonSlider クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider class
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
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
ms.openlocfilehash: 9f05ae7d0f3e1775a3321928867471749e11e679
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider クラス
`CMFCRibbonSlider`クラスがリボン バーまたはリボン ステータス バーに追加できるスライダー コントロールを実装します。 リボン スライダー コントロールは、Office 2007 アプリケーションに表示されるズーム スライダーに似ています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|構築し、リボン スライダー コントロールを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|スライダー コントロールの現在位置を返します。|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|スライダーの最大値を返します。|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|スライダーの最小値を返します。|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 (上書き[CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|スライダー コントロールのズーム インクリメントのサイズを返します。|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|スライダーにズーム ボタンがあるかどうかを指定します。|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (上書き[CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw))。|  
|[CMFCRibbonSlider::SetPos](#setpos)|スライダー コントロールの現在の位置を設定します。|  
|[CMFCRibbonSlider::SetRange](#setrange)|スライダー コントロールの範囲を指定するには、最小値と最大値を設定します。|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|ズーム ボタンの表示と非表示を切り替えます。|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|スライダー コントロールのズーム インクリメントのサイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 使用することができます、`SetRange`スライダーのズーム インクリメントの範囲を構成する方法です。 使用して、スライダーの現在位置を設定することができます、`SetPos`メソッドです。  
  
 左右のスライダー コントロールの右側に循環ズーム ボタンを表示するにを使用して、`SetZoomButtons`メソッドです。 既定では、スライダーは水平方向、左のズーム ボタンにマイナス記号を表示および右のズーム ボタンにプラス記号を表示します。  
  
 `SetZoomIncrement`メソッド定義を追加するか、ズーム ボタンをクリックすると、現在の位置から減算する増分します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonSlider`スライダーのプロパティを設定するクラス。 例では、作成する方法を示しています、`CMFCRibbonSlider`オブジェクト、ズーム ボタンの表示、スライダー コントロールの現在位置を設定およびスライダー コントロールの値の範囲を設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#12;](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonslider.h  
  
##  <a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider  
 リボン スライダーを構築します。  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 スライダーの id。  
  
 [in] です。 `nWidth`  
 スライダーの幅 (ピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 構築されるリボン スライダー`nWidth`スライダーの追加パネルのカテゴリの幅はピクセルです。 既定では、スライダーは水平方向です。  
  
##  <a name="getpos"></a>CMFCRibbonSlider::GetPos  
 スライダー コントロールの現在位置を返します。  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダーの先頭からの相対位置にあるスライダー コントロールの現在の位置。  
  
##  <a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax  
 スライダー コントロールのスライダーを移動できるスライダーの最大の増分値を取得します。  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールのスライダーを移動できるスライダーの最大インクリメントします。  
  
##  <a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin  
 スライダー コントロールのスライダーを移動できる最小の増分値を返します。  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールのスライダーを移動できる最小の移動量。  
  
##  <a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement  
 スライダー コントロールのズームの増分値を取得します。  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スライダー コントロールのズーム インクリメントします。  
  
##  <a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons  
 スライダーにズーム ボタンがあるかどうかを指定します。  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`スライダーにズーム ボタンがある場合`FALSE`それ以外の場合。  
  
##  <a name="ondraw"></a>CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpos"></a>CMFCRibbonSlider::SetPos  
 スライダー コントロールの現在の位置を設定します。  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nPos`  
 スライダーに設定する位置を指定します。 スライダーの先頭からの相対位置では。  
  
 [入力] `bRedraw`  
 場合`TRUE`スライダーが再描画されます。  
  
##  <a name="setrange"></a>CMFCRibbonSlider::SetRange  
 スライダー コントロールの値の範囲を設定します。  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMin`  
 スライダー コントロールの最小値を指定します。  
  
 [入力] `nMax`  
 スライダー コントロールの最大値を指定します。  
  
### <a name="remarks"></a>コメント  
 スライダー コントロールの値の範囲を指定するには、最小値と最大値を設定します。  
  
##  <a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons  
 表示と非表示のズーム ボタン。  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in] です。 `bSet`  
 `TRUE`ズーム ボタンを表示するには`FALSE`を非表示にします。  
  
##  <a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement  
 スライダー コントロールのズーム インクリメントを設定します。  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nZoomIncrement`  
 スライダー コントロールのズーム値を指定します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)

