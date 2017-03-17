---
title: "CMFCRibbonComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonComboBox class
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
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
ms.openlocfilehash: 747006ee66445eb312c22d658706e5fe81d2a958
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox クラス
`CMFCRibbonComboBox`クラスは、リボン バー、リボン パネル、またはリボン ポップアップ メニューに追加できるコンボ ボックス コントロールを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|リスト ボックスに一意の項目を追加します。|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|リスト ボックスから、指定した項目を削除します。|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|リスト ボックスのドロップダウンしたときにサイズを変更できるかどうかを指定します。|  
|[CMFCRibbonComboBox::FindItem](#finditem)|指定した文字列と一致するリスト ボックスでは、最初の項目のインデックスを返します。|  
|[CMFCRibbonComboBox::GetCount](#getcount)|リスト ボックスで、項目の数を返します。|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|リスト ボックスで現在選択されている項目のインデックスを取得します。|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|の一覧ボックスが削除されるときは、リスト ボックスの高さを取得します。|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|中間モードで表示されるように、コンボ ボックスのサイズを返します。|  
|[CMFCRibbonComboBox::GetItem](#getitem)|リスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します。|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|リスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します。|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|コントロールが編集ボックスに含まれるかどうかを示します。|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|リスト ボックスのサイズを変更できるかどうかを示します。|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|リスト ボックスで項目を選択するときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|リスト ボックスからすべての項目を削除し、編集ボックスをオフにします。|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|リスト ボックスの項目を選択します。|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|下へドロップしたときは、リスト ボックスの高さを設定します。|  
  
## <a name="remarks"></a>コメント  
 リボンのコンボ ボックスは、静的ラベルや、ユーザーが編集可能なラベルと組み合わせたリスト ボックスで構成されます。 リボン コンボ ボックスを作成する場合、どの種類を指定する必要があります。  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCRibbonComboBox`クラス、コンボ ボックスに項目を追加、コンボ ボックスで項目を選択、およびコンボ ボックスをパネルに追加します。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#11;](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribboncombobox.h  
  
##  <a name="additem"></a>CMFCRibbonComboBox::AddItem  
 リスト ボックスに一意の項目を追加します。  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszItem`  
 追加する項目の文字列です。  
  
 [入力] `dwData`  
 追加する項目に関連付けられているデータ。  
  
### <a name="return-value"></a>戻り値  
 追加する項目の&0; から始まるインデックス。  
  
##  <a name="cmfcribboncombobox"></a>CMFCRibbonComboBox::CMFCRibbonComboBox  
 `CMFCRibbonComboBox` オブジェクトを構築します。  
  
```  
public:  
CMFCRibbonComboBox(
    UINT nID,  
    BOOL bHasEditBox=TRUE,  
    Int nWidth=-1,  
    LPCTSTR lpszLabel=NULL,  
    Int nImage=-1);

protected:  
CMFCRibbonComboBox();
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コンボ ボックスの ID。  
  
 [入力] `bHasEditBox`  
 `TRUE`コントロール内で、編集ボックスを使用する場合`FALSE`それ以外の場合。  
  
 [入力] `nWidth`  
 ピクセル単位。 コンボ ボックスの幅または、既定の幅の場合は-1。  
  
 [入力] `lpszLabel`  
 コンボ ボックスの表示のラベルです。  
  
 [入力] `nImage`  
 コンボ ボックスの小さいイメージのインデックス。  
  
### <a name="remarks"></a>コメント  
 既定の幅は、108 ピクセルです。  
  
##  <a name="deleteitem"></a>CMFCRibbonComboBox::DeleteItem  
 リスト ボックスから、指定した項目を削除します。  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 削除する項目の&0; から始まるインデックス。  
  
 [入力] `dwData`  
 削除するアイテムに関連付けられているデータ。  
  
 [入力] `lpszText`  
 削除するアイテムの文字列。 複数のアイテムと同じ文字列がある場合は、最初の項目は削除されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定した項目が削除された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabledropdownlistresize"></a>CMFCRibbonComboBox::EnableDropDownListResize  
 リスト ボックスのドロップダウンしたときにサイズを変更できるかどうかを指定します。  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`サイズ変更を有効にするには`FALSE`サイズ変更を無効にします。  
  
### <a name="remarks"></a>コメント  
 サイズ変更を有効にすると、リスト ボックスに表示する項目に合わせてサイズが変わります。  
  
##  <a name="finditem"></a>CMFCRibbonComboBox::FindItem  
 指定した文字列と一致するリスト ボックスでは、最初の項目のインデックスを返します。  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszText`  
 リスト ボックス内の項目の文字列です。  
  
### <a name="return-value"></a>戻り値  
 項目の&0; から始まるインデックスまたは、項目が見つからなかった場合は-1。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcount"></a>CMFCRibbonComboBox::GetCount  
 リスト ボックスで、項目の数を返します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスまたはリスト ボックスに項目が含まれていない場合は 0 のアイテムの数。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcursel"></a>CMFCRibbonComboBox::GetCurSel  
 リスト ボックスで現在選択されている項目のインデックスを取得します。  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ボックスで現在選択されている項目の&0; から始まるインデックスまたは、項目が選択されていない場合は-1。  
  
##  <a name="getdropdownheight"></a>CMFCRibbonComboBox::GetDropDownHeight  
 の一覧ボックスが削除されるときは、リスト ボックスの高さを取得します。  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位) のリスト ボックスの高さ。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getintermediatesize"></a>CMFCRibbonComboBox::GetIntermediateSize  
 中間モードで表示されるように、コンボ ボックスのサイズを返します。  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 コンボ ボックスのデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックスのサイズ。  
  
### <a name="remarks"></a>コメント  
 小さいイメージを表示するとき、返されるサイズは、コンボ ボックスのサイズに基づいています。  
  
##  <a name="getitem"></a>CMFCRibbonComboBox::GetItem  
 リスト ボックスで指定したインデックス位置にある項目に関連付けられている文字列を返します。  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 リスト ボックス内の項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 アイテムに関連付けられている文字列へのポインターそれ以外の場合、`NULL`インデックス パラメーターが有効でない場合、またはインデックス パラメーターが-1 とコンボ ボックスで選択された項目がない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getitemdata"></a>CMFCRibbonComboBox::GetItemData  
 リスト ボックスで指定したインデックス位置にある項目に関連付けられているデータを返します。  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 リスト ボックス内の項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 項目に関連付けられたデータ0 または項目が存在しない場合、またはインデックス パラメーターが-1 とリスト ボックスで選択した項目がない場合。  
  
##  <a name="haseditbox"></a>CMFCRibbonComboBox::HasEditBox  
 コントロールが編集ボックスに含まれるかどうかを示します。  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`コントロールには、エディット ボックスが含まれている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isresizedropdownlist"></a>CMFCRibbonComboBox::IsResizeDropDownList  
 リスト ボックスのサイズを変更できるかどうかを示します。  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リスト ボックスのサイズを変更する場合それ以外の場合`FALSE`します。 [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>コメント  
 使用してリスト ボックスのサイズ変更を有効にする、 [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)メソッドです。  
  
##  <a name="onselectitem"></a>CMFCRibbonComboBox::OnSelectItem  
 ユーザーがリスト ボックスで項目を選択したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItem`  
 選択した項目のインデックス。  
  
### <a name="remarks"></a>コメント  
 ユーザー入力の選択を処理する場合は、このメソッドをオーバーライドします。  
  
##  <a name="removeallitems"></a>CMFCRibbonComboBox::RemoveAllItems  
 リスト ボックスからすべての項目を削除し、編集ボックスをオフにします。  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="selectitem"></a>CMFCRibbonComboBox::SelectItem  
 リスト ボックスの項目を選択します。  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
 リスト ボックス内の項目の&0; から始まるインデックス。  
  
 [入力] `dwData`  
 リスト ボックス内の項目に関連付けられたデータ。  
  
 [入力] `lpszText`  
 リスト ボックス内の項目の文字列です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdropdownheight"></a>CMFCRibbonComboBox::SetDropDownHeight  
 下へドロップしたときは、リスト ボックスの高さを設定します。  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nHeight`  
 (ピクセル単位) のリスト ボックスの高さ。  
  
### <a name="remarks"></a>コメント  
 既定の高さは、150 ピクセルです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit クラス](../../mfc/reference/cmfcribbonedit-class.md)

