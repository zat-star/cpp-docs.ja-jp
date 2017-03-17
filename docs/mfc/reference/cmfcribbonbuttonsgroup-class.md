---
title: "CMFCRibbonButtonsGroup クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup class
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2d8909ca63bd1d9121e1126d46a08312521cc4ac
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup クラス
`CMFCRibbonButtonsGroup`クラスでは、リボン ボタンのセットをグループに編成することができます。 グループ内のすべてのボタンは互いに隣接して水平に並べられ、1 つの枠で囲まれます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|`CMFCRibbonButtonsGroup` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|ボタンをグループに追加します。|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|ボタンのリストをグループに追加します。|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|指定したインデックス位置にあるボタンへのポインターを返します。|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|グループ内のボタンの数を返します。|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|リボン グループの通常のイメージのイメージのサイズを返します (オーバーライド[CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize))。|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|リボン要素の通常のサイズを返します (オーバーライド[CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|レポートするかどうか、`CMFCRibbonButtonsGroup`オブジェクトには、ツール バー イメージが含まれています。|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|ボタンは、標準、強調表示されているか無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|すべてのボタンの削除、`CMFCRibbonButtonsGroup`オブジェクトです。|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|画像をグループに割り当てます。|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|親を設定`CMFCRibbonCategory`の`CMFCRibbonButtonsGroup`オブジェクトとその中のすべてのボタン (オーバーライド[CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory))。|  
  
## <a name="remarks"></a>コメント  
 グループがから派生した[CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md)され、単一のエンティティとして操作することができます。 パネルまたはポップアップ メニューに、グループを配置することができます。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonButtonsGroup`クラスです。 例では、作成する方法を示しています、`CMFCRibbonButtonsGroup`オブジェクト、リボン ボタンのグループにイメージを割り当てたり、リボン ボタンのグループにボタンを追加します。 このコード スニペットの一部である、[クライアントの描画のサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonbuttonsgroup.h  
  
##  <a name="addbutton"></a>CMFCRibbonButtonsGroup::AddButton  
 ボタンをグループに追加します。  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 追加するボタンへのポインター。  
  
##  <a name="addbuttons"></a>CMFCRibbonButtonsGroup::AddButtons  
 ボタンのリストをグループに追加します。  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lstButtons`  
 追加するボタンへのポインターのリスト。  
  
##  <a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 `CMFCRibbonButtonsGroup` オブジェクトを構築します。  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 新しく作成されたに追加するボタンを指定`CMFCRibbonButtonsGroup`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton  
 指定したインデックス位置にあるボタンへのポインターを返します。  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `i`  
 返すボタンの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にあるボタンへのポインター。 `NULL`指定したインデックスが範囲外にある場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount  
 グループ内のボタンの数を返します。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グループ内のボタンの数。  
  
##  <a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize  
 保護対象のソース イメージのサイズを取得`CMFCToolBarImages`メンバー`m_Images`します。  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツール バー イメージのソース イメージのサイズを返しますが、存在する場合または`CSize`0 以外の場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize  
 リボン グループの要素で使用できる最大サイズを取得します。  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 リボン グループのデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages  
 レポートするかどうか、`CMFCRibbonButtonsGroup`オブジェクトには、ツール バー イメージが含まれています。  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>戻り値  
 True の場合、保護された`CMFCToolBarImages`メンバー`m_Images`画像、その場合は FALSE が含まれています。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage  
 ボタンは、標準、強調表示されているか無効になっているかどうかに応じて、指定したボタンの適切なイメージを描画します。  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonButtonsGroup`オブジェクトです。  
  
 [入力] `rectImage`  
 イメージを描画する四角形。  
  
 [入力] `pButton`  
 イメージを描画するためのボタンをクリックします。  
  
 [入力] `nImageIndex`  
 (通常、強調表示されている、または無効になっているボタンの&3; つのイメージの配列の&1; つ) のボタンを描画するイメージのインデックス。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll  
 すべてのボタンの削除、`CMFCRibbonButtonsGroup`オブジェクトです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages  
 リボンのボタンのグループには、イメージを割り当てます。  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pImages`  
 通常のイメージ。  
  
 [入力] `pHotImages`  
 ホット イメージ。  
  
 [入力] `pDisabledImages`  
 無効なイメージ。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetImages`ボタンをグループに追加する前にします。 イメージの数は、グループに追加するボタンの数以上にする必要があります。  
  
> [!NOTE]
>  ホット イメージとは、ボタン上に置いたときに表示されるイメージです。 無効なイメージとは、ボタンが無効になっているときに表示されるイメージです。  
  
##  <a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory  
 親を設定`CMFCRibbonCategory`の`CMFCRibbonButtonsGroup`オブジェクトとその中のすべてのボタンです。  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pCategory`  
 設定を親カテゴリへのポインター (リボン コントロールのタブ付きグループはカテゴリで呼ばれます)。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

