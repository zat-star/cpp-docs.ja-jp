---
title: "CAutoHideDockSite クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAutoHideDockSite"
  - "AllowShowOnPaneMenu"
  - "CAutoHideDockSite::AllowShowOnPaneMenu"
  - "CAutoHideDockSite.AllowShowOnPaneMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AllowShowOnPaneMenu メソッド"
  - "CAutoHideDockSite クラス"
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CAutoHideDockSite クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAutoHideDockSite` は、[CDockSite クラス](../../mfc/reference/cdocksite-class.md)を拡張して自動非表示のドッキング ペインを実装します。  
  
## 構文  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` オブジェクトを構築します。|  
|`CAutoHideDockSite::~CAutoHideDockSite`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|`CAutoHideDockSite` をペイン メニューに表示するかどうかを示します。|  
|[CAutoHideDockSite::CanAcceptPane](../Topic/CAutoHideDockSite::CanAcceptPane.md)|基本ペイン オブジェクトが [CMFCAutoHideBar クラス](../Topic/CMFCAutoHideBar%20Class.md)から派生したものかどうかを判断します。|  
|[CAutoHideDockSite::DockPane](../Topic/CAutoHideDockSite::DockPane.md)|ペインをこの `CAuotHideDockSite` オブジェクトにドッキングします。|  
|[CAutoHideDockSite::GetAlignRect](../Topic/CAutoHideDockSite::GetAlignRect.md)|画面座標でのドッキング サイトのサイズを取得します。|  
|[CAutoHideDockSite::RepositionPanes](../Topic/CAutoHideDockSite::RepositionPanes.md)|グローバルなマージンとボタン間のスペースで `CAutoHideDockSite` にペインを再描画します。|  
|[CAutoHideDockSite::SetOffsetLeft](../Topic/CAutoHideDockSite::SetOffsetLeft.md)|ドッキング バーの左側のマージンを設定します。|  
|[CAutoHideDockSite::SetOffsetRight](../Topic/CAutoHideDockSite::SetOffsetRight.md)|ドッキング バーの右側のマージンを設定します。|  
|[CAutoHideDockSite::UnSetAutoHideMode](../Topic/CAutoHideDockSite::UnSetAutoHideMode.md)|`CAutoHideDockSite` 上のオブジェクトに対して [CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md) を呼び出します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|[CAutoHideDockSite::m\_nExtraSpace](../Topic/CAutoHideDockSite::m_nExtraSpace.md)|ツール バーとドッキング バーの端の間の領域のサイズを定義します。  この領域は、ドッキング領域の配置に応じて、左端または上端から測定されます。|  
  
## 解説  
 [CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md) を呼び出すと、フレームワークにより自動的に `CAutoHideDockSite` オブジェクトが作成されます。  ほとんどの場合、このクラスを直接インスタンス化したり使用したりする必要はありません。  
  
 ドッキング バーは、ドッキング ペインの左側と、[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)の左側との間のギャップです。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## 使用例  
 `CMFCAutoHideBar` オブジェクトから `CAutoHideDockSite` オブジェクトを取得する方法と、ドッキング バーの左右のマージンを設定する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/CPP/cautohidedocksite-class_1.cpp)]  
  
## 必要条件  
 **ヘッダー :** afxautohidedocksite.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockSite クラス](../../mfc/reference/cdocksite-class.md)