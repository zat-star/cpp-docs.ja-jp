---
title: "CMFCToolBarInfo クラス | Microsoft Docs"
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
  - "CMFCToolBarInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarInfo クラス"
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

さまざまな状態のツール バー イメージのリソース ID を含みます。  `CMFCToolBarInfo` は、[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md) メソッドのパラメーターとして使用されるヘルパー クラスです。  
  
## 構文  
  
```  
class CMFCToolBarInfo  
```  
  
## メンバー  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarInfo::m\_uiColdResID](../Topic/CMFCToolBarInfo::m_uiColdResID.md)|標準 \(コールド\) のツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiDisabledResID](../Topic/CMFCToolBarInfo::m_uiDisabledResID.md)|無効なツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiHotResID](../Topic/CMFCToolBarInfo::m_uiHotResID.md)|選択した \(ホット\) ツール バーのイメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiLargeColdResID](../Topic/CMFCToolBarInfo::m_uiLargeColdResID.md)|標準の大きいツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiLargeDisabledResID](../Topic/CMFCToolBarInfo::m_uiLargeDisabledResID.md)|無効な大きいツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiLargeHotResID](../Topic/CMFCToolBarInfo::m_uiLargeHotResID.md)|選択した大きいツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiMenuDisabledResID](../Topic/CMFCToolBarInfo::m_uiMenuDisabledResID.md)|無効なメニュー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m\_uiMenuResID](../Topic/CMFCToolBarInfo::m_uiMenuResID.md)|メニュー イメージを含むツール バー ビットマップのリソース ID。|  
  
## 解説  
 ツール バーの完全なビットマップは、固定サイズの小さいツール バー イメージ \(ボタン\) で構成されます。  `CMFCToolBarInfo` オブジェクトに保存されているそれぞれのリソース ID が、1 つの状態 \(たとえば、選択したイメージ、無効のイメージ、大きいイメージ、またはメニュー イメージ\) のツール バー イメージの完全なセットを含むビットマップであることを確認してください。  
  
## 継承階層  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)