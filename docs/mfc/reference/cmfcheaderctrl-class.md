---
title: "CMFCHeaderCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
dev_langs:
- C++
helpviewer_keywords:
- CMFCHeaderCtrl class
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
caps.latest.revision: 29
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
ms.openlocfilehash: c49ee61b6441e79a0c3c4c1aa133b4bce1578103
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class
`CMFCHeaderCtrl`クラスは、ヘッダー コントロールの複数の列の並べ替えをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|`CMFCHeaderCtrl` オブジェクトを構築します。|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|有効または無効に*複数列の並べ替え*の現在のヘッダー コントロールのモードです。|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|列が並べ替えられていないかを昇順または降順で並べ替えるかどうかを示します。|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|ヘッダー コントロールの最初の並べ替えられた列の&0; から始まるインデックスを取得します。|  
|`CMFCHeaderCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|ヘッダー コントロールの任意の列を昇順で並べ替えるかどうかを示します。|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|現在のヘッダー コントロールの親ウィンドウがダイアログ ボックスであるかどうかを示します。|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|現在のヘッダー コントロールがあるかどうかを示す*複数列の並べ替え*モードです。|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|並べ替え列のリストから指定された列を削除します。|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|ヘッダー コントロールの指定された列の並べ替え順序を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|ヘッダー コントロールの列を描画するためにフレームワークによって呼び出されます。|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|並べ替えの矢印を描画するためにフレームワークによって呼び出されます。|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|ヘッダー コントロールの列の背景を塗りつぶすために、フレームワークによって呼び出されます。|  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCHeaderCtrl`クラス、および有効にする方法*複数列の並べ替え*の現在のヘッダー コントロールのモードです。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&24;](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>コメント  
 `CMFCHeaderCtrl`クラスは、列を並べ替えることを示すためにヘッダー コントロールの列の並べ替えの矢印を描画します。 使用*複数列の並べ替え*モードの場合は、親のリスト コントロール内の列のセット ( [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md))、同時に並べ替えることができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxheaderctrl.h  
  
##  <a name="cmfcheaderctrl"></a>CMFCHeaderCtrl::CMFCHeaderCtrl  
 `CMFCHeaderCtrl` オブジェクトを構築します。  
  
```  
CMFCHeaderCtrl::CMFCHeaderCtrl()  
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターは、指定した値には、次のメンバー変数を初期化します。  
  
|メンバー変数|値|  
|---------------------|-----------|  
|`m_bIsMousePressed`|`FALSE`|  
|`m_bMultipleSort`|`FALSE`|  
|`m_bAscending`|`TRUE`|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|`FALSE`|  
|`m_bIsDlgControl`|`FALSE`|  
|`m_hFont`|`NULL`|  
  
##  <a name="enablemultiplesort"></a>CMFCHeaderCtrl::EnableMultipleSort  
 有効または無効に*複数列の並べ替え*の現在のヘッダー コントロールのモードです。  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`複数列の並べ替えモードを有効にするには`FALSE`を複数の列の並べ替えモードを無効にして、並べ替えられた列の一覧から列を削除します。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
 有効にするか、複数の列の並べ替えモードを無効にするには、このメソッドを使用します。 ヘッダー コントロールが複数の列の並べ替えモードの場合、2 つ以上の列は、並べ替えに参加できます。  
  
##  <a name="getcolumnstate"></a>CMFCHeaderCtrl::GetColumnState  
 列が並べ替えではありませんかを昇順または降順で並べ替えるかどうかを示します。  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 列の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定された列の並べ替えの状態を示す値。 次の表では、指定できる値を示します。  
  
|値|説明|  
|-----------|-----------------|  
|-1|降順に並べ替えられます。|  
|0|並べ替えられていません。|  
|1|昇順に並べ替えられます。|  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getsortcolumn"></a>CMFCHeaderCtrl::GetSortColumn  
 ヘッダー コントロールの最初の並べ替えられた列の&0; から始まるインデックスを取得します。  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>戻り値  
 並べ替える列または並べ替えられた列が存在しない場合は-1 のインデックス。  
  
### <a name="remarks"></a>コメント  
 ヘッダー コントロールが場合*複数列の並べ替え*モードと、このメソッドは、アサートしを使用するように勧めるデバッグ モードでアプリケーションをコンパイル、 [CMFCHeaderCtrl::GetColumnState](#getcolumnstate)メソッド代わりにします。 ヘッダー コントロールが複数の列の並べ替えモードになって、リテール モードでアプリケーションをコンパイルした場合は、このメソッドは-1 を返します。  
  
##  <a name="isascending"></a>CMFCHeaderCtrl::IsAscending  
 ヘッダー コントロールの任意の列を昇順で並べ替えるかどうかを示します。  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ヘッダー コントロールの任意の列が昇順に並べ替えられている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドから返される値は、ヘッダー コントロールの項目に適切な並べ替えの矢印を表示するために使用します。 使用して、 [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)並べ替え順序を設定します。  
  
##  <a name="isdialogcontrol"></a>CMFCHeaderCtrl::IsDialogControl  
 現在のヘッダー コントロールの親ウィンドウがダイアログ ボックスであるかどうかを示します。  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`現在のヘッダー コントロールの親ウィンドウが、ダイアログ ボックスである場合それ以外の場合、`FALSE`です。  
  
##  <a name="ismultiplesort"></a>CMFCHeaderCtrl::IsMultipleSort  
 現在のヘッダー コントロールがあるかどうかを示す*複数列の並べ替え*モードです。  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`複数列の並べ替えモードが有効にします。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)メソッドを有効または複数の列の並べ替えモードを無効にします。 ヘッダー コントロールが複数の列の並べ替えモードの場合、2 つ以上の列は、並べ替えに参加できます。  
  
##  <a name="ondrawitem"></a>CMFCHeaderCtrl::OnDrawItem  
 ヘッダー コントロールの列を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `iItem`  
 描画する項目の&0; から始まるインデックス。  
  
 [入力] `rect`  
 描画する項目の外接する四角形。  
  
 [入力] `bIsPressed`  
 `TRUE`押された状態で、項目を描画するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bIsHighlighted`  
 `TRUE`強調表示された状態で、項目を描画するにはそれ以外の場合、`FALSE`です。  
  
##  <a name="ondrawsortarrow"></a>CMFCHeaderCtrl::OnDrawSortArrow  
 並べ替えの矢印を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectArrow`  
 並べ替え矢印の外接する四角形。  
  
##  <a name="onfillbackground"></a>CMFCHeaderCtrl::OnFillBackground  
 ヘッダー コントロールの列の背景を塗りつぶすために、フレームワークによって呼び出されます。  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removesortcolumn"></a>CMFCHeaderCtrl::RemoveSortColumn  
 並べ替え列のリストから指定された列を削除します。  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 削除する列の&0; から始まるインデックス。  
  
##  <a name="setsortcolumn"></a>CMFCHeaderCtrl::SetSortColumn  
 ヘッダー コントロールの指定された列の並べ替え順序を設定します。  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 ヘッダー コントロールの列の&0; から始まるインデックス。 このパラメーターが&0; より小さい場合、このメソッドは、並べ替え列のリストからすべての列を削除します。  
  
 [入力] `bAscending`  
 列の並べ替え順序を指定する、`iColumn`パラメーターを指定します。 `TRUE`昇順。 を設定するには`FALSE`を降順に並べ替えを設定します。 既定値は `TRUE` です。  
  
 [入力] `bAdd`  
 `TRUE`列の並べ替え順序の設定、`iColumn`パラメーターを指定します。  
  
 現在のヘッダー コントロールが場合*複数列の並べ替え*モードでは、このメソッドは、並べ替え列のリストに指定された列を追加します。 使用[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)を複数の列の並べ替えモードを設定します。  
  
 かどうかは、複数の列の並べ替えモードが設定されていないと、このメソッドは、デバッグ モードでコンパイルされている、このメソッドはアサートします。 複数列の並べ替えモードが設定されていない、このメソッドは、製品版モードでコンパイルされている場合は、このメソッドは最初並べ替え列の一覧からすべての列を削除し、一覧に指定された列を追加します。  
  
 `FALSE`最初に並べ替え列の一覧からすべての列を削除し、一覧に指定された列を追加します。 既定値は `FALSE` です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、列の並べ替え順序を設定できます。 必要に応じて、このメソッドは、列を並べ替え列のリストに追加します。 ヘッダー コントロールでは、並べ替え順序を使用して、上向きまたは下向きの矢印を描画します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)

