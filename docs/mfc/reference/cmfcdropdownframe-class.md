---
title: "CMFCDropDownFrame クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDropDownFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownFrame クラス"
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownFrame クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ドロップダウン ツール バーとドロップダウン ツール バー ボタンにドロップダウン フレーム ウィンドウ機能を提供します。  
  
## 構文  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|既定のコンストラクターです。|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDropDownFrame::Create](../Topic/CMFCDropDownFrame::Create.md)|`CMFCDropDownFrame` オブジェクトを作成します。|  
|`CMFCDropDownFrame::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCDropDownFrame::GetParentMenuBar](../Topic/CMFCDropDownFrame::GetParentMenuBar.md)|ドロップダウン フレームの親メニュー バーを取得します。|  
|[CMFCDropDownFrame::GetParentPopupMenu](../Topic/CMFCDropDownFrame::GetParentPopupMenu.md)|ドロップダウン フレームの親ポップアップ メニューを取得します。|  
|`CMFCDropDownFrame::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCDropDownFrame::RecalcLayout](../Topic/CMFCDropDownFrame::RecalcLayout.md)|ドロップダウン フレームを再配置します。|  
|[CMFCDropDownFrame::SetAutoDestroy](../Topic/CMFCDropDownFrame::SetAutoDestroy.md)|子ドロップダウン ツール バー ウィンドウを自動的に破棄するかどうかを設定します。|  
  
### 解説  
 このクラスは、コードで直接使用するためのものではありません。  
  
 フレームワークは、このクラスを使用して `CMFCDropDownToolbar` および `CMFCDropDownToolbarButton` クラスにフレーム動作を提供します。  これらのクラスの詳細については、「[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)」と「[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)」を参照してください。  
  
## 使用例  
 `CMFCDropDownFrame` オブジェクトへのポインターを `CFrameWnd` クラスから取得する方法と、子ドロップダウン ツール バー ウィンドウを自動的に破棄するように設定する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/CPP/cmfcdropdownframe-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdropdowntoolbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)