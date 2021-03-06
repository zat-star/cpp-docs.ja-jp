---
title: "CMFCRibbonGalleryMenuButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a50dd19b15e9510bd5d1ca504209caecaf195fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbongallerymenubutton-class"></a>CMFCRibbonGalleryMenuButton クラス
リボン ギャラリーを含むリボン メニュー ボタンを実装します。  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
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
|[CMFCRibbonGalleryMenuButton::CopyFrom](#copyfrom)|(上書き[cmfctoolbarmenubutton::copyfrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom))。|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](#createpopupmenu)|(上書き[cmfctoolbarmenubutton::createpopupmenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu))。|  
|[CMFCRibbonGalleryMenuButton::GetPalette](#getpalette)||  
|[CMFCRibbonGalleryMenuButton::HasButton](#hasbutton)|(`CMFCToolBarMenuButton::HasButton` をオーバーライドします)。|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|(上書き[cmfctoolbarmenubutton::isemptymenuallowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed))。|  
  
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxRibbonPaletteGallery.h  
  
##  <a name="copyfrom"></a>CMFCRibbonGalleryMenuButton::CopyFrom  

  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcribbongallerymenubutton"></a>CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton  
 構築して初期化、 [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)オブジェクト。  
  
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
 ボタンのコマンド ID。 これで送信される値は、 **WM_COMMAND**メッセージが表示される、このボタンをクリックします。  
  
 `iImage`  
 ギャラリー メニュー ボタンに表示するイメージのインデックス。 イメージが格納されている、`imagesPalette`パラメーター。  
  
 `lpszText`  
 メニュー ボタンに表示するテキスト。  
  
 `imagesPalette`  
 ギャラリーに表示するイメージの一覧が含まれています。  
  
 `uiImagesPaletteResID`  
 ギャラリーに表示するイメージのイメージ リストのリソース ID。  
  
 `cxPaletteImage`  
 ギャラリーに表示するイメージのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 ギャラリー メニュー ボタンは、矢印がポップアップ メニューとして表示されます。 ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。  
  
### <a name="example"></a>例  
 次の例でのコンス トラクターを使用する方法、`CMFCRibbonGalleryMenuButton`クラスです。 このコード スニペットの一部である、 [MS Office 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]  
  
##  <a name="createpopupmenu"></a>CMFCRibbonGalleryMenuButton::CreatePopupMenu  

  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpalette"></a>CMFCRibbonGalleryMenuButton::GetPalette  

  
```  
CMFCRibbonGallery& GetPalette();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasbutton"></a>CMFCRibbonGalleryMenuButton::HasButton  

  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isemptymenuallowed"></a>CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed  

  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)
