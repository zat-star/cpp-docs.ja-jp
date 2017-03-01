---
title: "CMFCRibbonGalleryMenuButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGalleryMenuButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton class
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dce01ac22db0ff28e8f07b6d30f6418a61ad68d5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton クラス
リボン ギャラリーを含むリボン メニュー ボタンを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](#cmfcribbongallerymenubutton)|`CMFCRibbonGalleryMenuButton` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|(上書き[CMFCToolBarMenuButton::CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom))。|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(上書き[CMFCToolBarMenuButton::CreatePopupMenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu))。|  
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||  
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(`CMFCToolBarMenuButton::HasButton` をオーバーライドします)。|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(上書き[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed))。|  
  
### <a name="remarks"></a>コメント  
 ギャラリー メニュー ボタンが、矢印付きのポップアップ メニューとして表示されます。 ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。 ギャラリー メニュー ボタンを構築する場合は、それらのイメージが含まれているイメージ リストを指定する必要があります。  
  
## <a name="example"></a>例  
 次の例は、メニュー ボタンに行頭記号のギャラリーを表示する方法を示しています。  
  
```  
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)  
{  
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)  
 {  
    CMFCToolBarButton* pExButton = 
    pMenuBar->GetButton(nBulletIndex);
ASSERT_VALID (pExButton);

    CMFCRibbonGalleryMenuButton paletteBullet (
    pExButton->m_nID, 
    pExButton->GetImage (),  
    pExButton->m_strText);

 InitBulletPalette (&paletteBullet.GetPalette ());

    pMenuBar->ReplaceButton (ID_PARA_BULLETS,
    paletteBullet);

 }  
}  
```  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonPaletteGallery.h  
  
##  <a name="a-namecopyfroma--cmfcribbongallerymenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCRibbonGalleryMenuButton::CopyFrom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecmfcribbongallerymenubuttona--cmfcribbongallerymenubuttoncmfcribbongallerymenubutton"></a><a name="cmfcribbongallerymenubutton"></a>CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton  
 構築して初期化、 [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)オブジェクトです。  
  
```  
CMFCRibbonGalleryMenuButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGalleryMenuButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText,  
    UINT uiImagesPaletteResID = 0,  
    int cxPaletteImage = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `uiID`  
 ボタンのコマンド ID。 これで送信される値は、 **WM_COMMAND**このボタンをクリックすると、メッセージです。  
  
 `iImage`  
 ギャラリーのメニュー ボタンを表示するイメージのインデックス。 イメージが格納されている、`imagesPalette`パラメーター。  
  
 `lpszText`  
 メニュー ボタンを表示するテキスト。  
  
 `imagesPalette`  
 ギャラリーに表示するイメージの一覧が含まれています。  
  
 `uiImagesPaletteResID`  
 ギャラリーに表示するイメージのイメージ リストのリソース ID です。  
  
 `cxPaletteImage`  
 ギャラリーに表示するイメージのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 ギャラリーのメニュー ボタンは、矢印がポップアップ メニューとして表示されます。 ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。  
  
### <a name="example"></a>例  
 次の例では、コンス トラクターを使用して、`CMFCRibbonGalleryMenuButton`クラスです。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#8;](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]  
  
##  <a name="a-namecreatepopupmenua--cmfcribbongallerymenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCRibbonGalleryMenuButton::CreatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetpalettea--cmfcribbongallerymenubuttongetpalette"></a><a name="getpalette"></a>CMFCRibbonGalleryMenuButton::GetPalette  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonGallery& GetPalette();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namehasbuttona--cmfcribbongallerymenubuttonhasbutton"></a><a name="hasbutton"></a>CMFCRibbonGalleryMenuButton::HasButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisemptymenualloweda--cmfcribbongallerymenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)

