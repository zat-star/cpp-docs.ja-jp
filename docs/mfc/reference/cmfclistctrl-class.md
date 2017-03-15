---
title: "CMFCListCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCListCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCListCtrl class
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
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
ms.openlocfilehash: 3a4c67b2d7ea2a5356f7c053403edf414319a928
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl クラス
`CMFCListCtrl`クラスの機能を拡張する[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラスの高度なヘッダー コントロールの機能をサポートすることによって、 [CMFCHeaderCtrl クラス](../../mfc/reference/cmfcheaderctrl-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|別の背景色で並べ替えられた列をマークすることを有効にします。|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|複数の並べ替えモードを有効にします。|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|下線が引かれたヘッダー コントロールへの参照を返します。|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|かどうか、リスト コントロールが複数の並べ替えモードを確認します。|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|2 つのリスト コントロール項目を比較する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|個々 のセルの背景色を確認する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|描画されるセルのフォントを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|個々 のセルのテキストの色を確認する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|並べ替えられた列の一覧から並べ替え列を削除します。|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|現在の並べ替え列と並べ替え順序を設定します。|  
|[CMFCListCtrl::Sort](#sort)|リスト コントロールを並べ替えます。|  
  
## <a name="remarks"></a>コメント  
 `CMFCListCtrl`2 つの拡張は、 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラスです。 最初に、自動的にヘッダーの並べ替えの矢印を描画することによって利用可能なオプションでは列の並べ替えことを示します。 次に、データの同時に複数の列で並べ替えをサポートします。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCListCtrl`クラスです。 この例では、リスト コントロールを作成、列を挿入する、項目を挿入、アイテムのテキストを設定およびリスト コントロールのフォントを設定する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#25;](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&26;](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxlistctrl.h  
  
##  <a name="a-nameenablemarksortedcolumna--cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn  
 別の背景色で並べ替えられた列をマークします。  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMark`  
 別の背景色を有効にするかどうかを決定するブール値パラメーター。  
  
 [入力] `bRedraw`  
 コントロールをすぐに再描画するかどうかを決定するブール値パラメーター。  
  
### <a name="remarks"></a>コメント  
 `EnableMarkSortedColumn`メソッドを使用して`CDrawingManager::PixelAlpha`に使用する色を計算する列を並べ替えます。 選択される色は、標準の背景色に基づいています。  
  
##  <a name="a-nameenablemultiplesorta--cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort  
 複数の列でリスト コントロール内のデータの行の並べ替えを有効にします。  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 複数の列の並べ替えモードを有効にするかどうかを指定するブール値。  
  
### <a name="remarks"></a>コメント  
 複数の列に基づく並べ替えを有効にすると、列は、階層がある操作を行います。 データの行は、まずプライマリ列によって並べ替えられます。 対応する値は、優先順位に基づく後続の各列で並べ替えられます。  
  
##  <a name="a-namegetheaderctrla--cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl  
 ヘッダー コントロールへの参照を返します。  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 基になるへの参照を[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 リスト コントロールのヘッダー コントロールは、列のタイトルを含むウィンドウです。 これは通常、列のすぐ上にあります。  
  
##  <a name="a-nameismultiplesorta--cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort  
 リスト コントロール現在がサポートするか複数の列で並べ替えを確認します。  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リスト コントロールには、複数の並べ替えがサポートされている場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 ときに、 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)が複数の並べ替えをサポート、ユーザーは、複数の列でリスト コントロール内のデータを並べ替えることができます。 複数の並べ替えを有効にする[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)します。  
  
##  <a name="a-nameoncompareitemsa--cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems  
 フレームワークは、2 つの項目を比較するときに、このメソッドを呼び出します。  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lParam1`  
 比較する最初の項目です。  
  
 [入力] `lParam2`  
 比較する&2; 番目の項目です。  
  
 [入力] `iColumn`  
 このメソッドを並べ替え列のインデックス。  
  
### <a name="return-value"></a>戻り値  
 2 つのアイテムの相対位置を示す整数。 負の値を最初の項目が&2; つ目の前に付けてくださいで示して正の値を示している最初の項目が、2 番目に従う必要があり、0 は、2 つの項目が同等であることを意味します。  
  
### <a name="remarks"></a>コメント  
 常に既定の実装では、0 を返します。 並べ替えアルゴリズムを指定するには、この関数をオーバーライドする必要があります。  
  
##  <a name="a-nameongetcellbkcolora--cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor  
 フレームワークは、個々 のセルの背景色を確認する必要があるときに、このメソッドを呼び出します。  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列。  
  
### <a name="return-value"></a>戻り値  
 A`COLOREF`セルの背景色を指定する値。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnGetCellBkColor`指定された入力パラメーターは使用されないため、代わりを呼び出すだけ`GetBkColor`します。 そのため、既定では、リスト コントロール全体は、同一の背景色があります。 オーバーライドできます`OnGetCellBkColor`を別の背景色で個々 のセルをマークする派生クラスでします。  
  
##  <a name="a-nameongetcellfonta--cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont  
 フレームワークは、個々 のセルのフォントを取得する場合に、このメソッドを呼び出します。  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列。  
  
 [入力] `dwData`  
 ユーザー定義データ。 既定の実装では、このパラメーターを使用しません。  
  
### <a name="return-value"></a>戻り値  
 現在のセルで使用されているフォントへのハンドル。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドが戻る`NULL`します。 リスト コントロール内のセルのすべてで同じフォントがあります。 各セルでさまざまなフォントを提供するために、このメソッドをオーバーライドします。  
  
##  <a name="a-nameongetcelltextcolora--cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor  
 フレームワークは、個々 のセルのテキストの色を確認する必要がありますがある場合、このメソッドを呼び出します。  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列。  
  
### <a name="return-value"></a>戻り値  
 A`COLOREF`セルのテキストの色を指定する値。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドを呼び出す`GetTextColor`入力パラメーターに関係なく。 リスト コントロール全体は、同じテキストの色があります。 オーバーライドできます`OnGetCellTextColor`を別のテキストの色で個々 のセルをマークする派生クラスでします。  
  
##  <a name="a-nameremovesortcolumna--cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn  
 並べ替えられた列の一覧から並べ替え列を削除します。  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 削除する列。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ヘッダー コントロールから並べ替え列を削除します。 呼び出す[CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)します。  
  
##  <a name="a-namesetsortcolumna--cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn  
 現在の並べ替え列と並べ替え順序を設定します。  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 並べ替える列。  
  
 [入力] `bAscending`  
 並べ替え順序を指定するブール値。  
  
 [入力] `bAdd`  
 メソッドがによって示される列を追加するかどうかを指定するブール値`iColumn`並べ替え列の一覧にします。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、メソッドを使用してヘッダー コントロールへの入力パラメーターを渡します[CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)します。  
  
##  <a name="a-namesorta--cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::Sort  
 リスト コントロールを並べ替えます。  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 並べ替える列。  
  
 [入力] `bAscending`  
 並べ替え順序を指定するブール値。  
  
 [入力] `bAdd`  
 このメソッドがによって示される列を追加するかどうかを指定するブール値`iColumn`並べ替え列の一覧にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)

