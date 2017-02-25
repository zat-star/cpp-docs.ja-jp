---
title: "CMFCRibbonGalleryMenuButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonGalleryMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonGalleryMenuButton クラス"
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonGalleryMenuButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リボン ギャラリーを含むリボン メニュー ボタンを実装します。  
  
## 構文  
  
```  
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton](../Topic/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton.md)|`CMFCRibbonGalleryMenuButton` オブジェクトを構築して初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonGalleryMenuButton::CopyFrom](../Topic/CMFCRibbonGalleryMenuButton::CopyFrom.md)|\([CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md) をオーバーライドします\)。|  
|[CMFCRibbonGalleryMenuButton::CreatePopupMenu](../Topic/CMFCRibbonGalleryMenuButton::CreatePopupMenu.md)|\([CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md) をオーバーライドします\)。|  
|[CMFCRibbonGalleryMenuButton::GetPalette](../Topic/CMFCRibbonGalleryMenuButton::GetPalette.md)||  
|[CMFCRibbonGalleryMenuButton::HasButton](../Topic/CMFCRibbonGalleryMenuButton::HasButton.md)|\(`CMFCToolBarMenuButton::HasButton` をオーバーライドします\)。|  
|[CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed](../Topic/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed.md)|\([CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md) をオーバーライドします\)。|  
  
### コメント  
 ギャラリー メニュー ボタンが、矢印付きのポップアップ メニューとして表示されます。  ユーザーがこのボタンをクリックすると、イメージのギャラリーが表示されます。  ギャラリー メニュー ボタンを構築する場合は、それらのイメージが含まれているイメージ リストを指定する必要があります。  
  
## 使用例  
 次の例は、メニュー ボタンに行頭記号のギャラリーを表示する方法を示しています。  
  
```  
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)  
{  
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);  
    if (nBulletIndex >= 0)  
    {  
        CMFCToolBarButton* pExButton =  
            pMenuBar->GetButton(nBulletIndex);  
        ASSERT_VALID (pExButton);  
        CMFCRibbonGalleryMenuButton paletteBullet (  
            pExButton->m_nID,  
            pExButton->GetImage (),  
            pExButton->m_strText);  
        InitBulletPalette (&paletteBullet.GetPalette ());  
        pMenuBar->ReplaceButton (ID_PARA_BULLETS, paletteBullet);  
    }  
}  
```  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCRibbonGalleryMenuButton](../../mfc/reference/cmfcribbongallerymenubutton-class.md)  
  
## 必要条件  
 **ヘッダー:** afxRibbonPaletteGallery.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)