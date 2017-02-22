---
title: "CMFCImageEditorPaletteBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImageEditorPaletteBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorPaletteBar クラス"
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCImageEditorPaletteBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イメージ エディター ダイアログ ボックスにパレット バー機能を提供します。  
  
## 構文  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImageEditorPaletteBar::GetRowHeight](../Topic/CMFCImageEditorPaletteBar::GetRowHeight.md)|ツール バー ボタンの高さを返します。  \([CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md) をオーバーライドします\)。|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](../Topic/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable.md)|拡張された境界を持つボタンをツール バーが表示できるかどうかを判断します   \([CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md) をオーバーライドします\)。|  
  
### 解説  
 このクラスは、コードで直接使用するためのものではありません。  
  
 フレームワークは、このクラスを使用してイメージ エディター ダイアログ ボックスにパレット バーを表示します。  イメージ エディター ダイアログ ボックスの詳細については、「[CMFCImageEditorDialog クラス](../Topic/CMFCImageEditorDialog%20Class.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## 必要条件  
 **ヘッダー :** afximageeditordialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCImageEditorDialog クラス](../Topic/CMFCImageEditorDialog%20Class.md)