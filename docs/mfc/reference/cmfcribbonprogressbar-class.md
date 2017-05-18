---
title: "CMFCRibbonProgressBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar class
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
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
ms.openlocfilehash: 51efd8c4ac84dffe1384b7d664197b4bdebad110
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar クラス
時間のかかる操作の進行状況を視覚的に示すコントロールを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|現在の進行状況を返します。|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|現在の範囲の最大値を返します。|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|現在の範囲の最小値を返します。|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 (上書き[CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|進行状況バーが無限のモードで動作しているかどうかを指定します。|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (上書き[CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw))。|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|無限のモードで動作する進行状況バーを設定します。|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|現在の進行状況を設定します。|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|最小値と最大値を設定します。|  
  
## <a name="remarks"></a>コメント  
 A`CMFCRibbonProgressBar`は&2; つのモードで動作します。 定期的かつ無限です。 通常モードで進行状況バーは左から右に、最大値に達すると停止されます。 無限のモードでは、進行状況バーは繰り返しに最小値から最大値に入力されます。 無限のモードを使用すると、待機操作を継続的な完了時間が不明である可能性があります。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonProgressBar`クラスです。 進行状況バーの最小値と最大値を設定し、進行状況バーの現在位置の設定は、(ここで、操作の完了時間が不明) 無限モードで動作する進行状況バーを設定する方法を示します。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#11;](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 構築して初期化、 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)オブジェクトです。  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 リボンの進行状況バーのコマンド ID を指定します。  
  
 [入力] `nWidth`  
 リボンの進行状況バーのピクセル単位の幅を指定します。  
  
 [入力] `nHeight`  
 リボンの進行状況バーのピクセルで高さを指定します。  
  
##  <a name="getpos"></a>CMFCRibbonProgressBar::GetPos  
 進行状況バーの現在位置を返します。  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バーの現在位置を表す値。  
  
### <a name="remarks"></a>コメント  
 設定されている範囲が指定した範囲内になければなりません、 [CMFCRibbonProgressBar::SetRange](#setrange)メソッドです。  
  
##  <a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax  
 進行状況バーの現在の返す最大値。  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の範囲の最大値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin  
 進行状況バーの現在の取得範囲の最小値。  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の範囲の最小値。  
  
##  <a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode  
 進行状況バーが無限のモードで動作しているかどうかを指定します。  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`進行状況バーが無限モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 無限のモードでは、進行状況バーは最小値から最大値に繰り返し塗りつぶされます。 無限のモードを使用すると、待機操作を継続的な完了時間が不明である可能性があります。  
  
##  <a name="ondraw"></a>CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode  
 無限のモードで動作する進行状況バーを設定します。  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE`進行状況バーが無限モードであることを指定するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 通常は、進行状況バーが無限のモードの場合は、それをユーザーに通知操作が進行中であるが、完了時間が不明であります。 そのため、進行状況バー繰り返し塗りつぶさ最小値から最大値にします。  
  
##  <a name="setpos"></a>CMFCRibbonProgressBar::SetPos  
 進行状況バーの現在位置を設定します。  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nPos`  
 進行状況バーが設定されている位置を指定します。  
  
 [入力] `bRedraw`  
 進行状況バーを再描画されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 設定されている範囲が指定した範囲内になければなりません、 [CMFCRibbonProgressBar::SetRange](#setrange)メソッドです。  
  
##  <a name="setrange"></a>CMFCRibbonProgressBar::SetRange  
 進行状況バーの最小値と最大値を設定します。  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMin`  
 範囲の最小値を指定します。  
  
 [入力] `nMax`  
 範囲の最大値を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、最小値と最大値を設定して進行状況バーの範囲を定義します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)

