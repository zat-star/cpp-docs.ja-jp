---
title: "CTooltipManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTooltipManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTooltipManager クラス"
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CTooltipManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ツールヒントに関するランタイム情報を保持します。  `CTooltipManager` クラスのインスタンスは、アプリケーションごとに 1 回作成されます。  
  
## 構文  
  
```  
class CTooltipManager : public CObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTooltipManager::CreateToolTip](../Topic/CTooltipManager::CreateToolTip.md)|指定された Windows コントロールの種類のツールヒント コントロールを作成します。|  
|[CTooltipManager::DeleteToolTip](../Topic/CTooltipManager::DeleteToolTip.md)|ツールヒント コントロールを削除します。|  
|[CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md)|指定された Windows コントロールの種類のツールヒント コントロールの外観をカスタマイズします。|  
|[CTooltipManager::SetTooltipText](../Topic/CTooltipManager::SetTooltipText.md)|ツールヒント コントロールのテキストと説明を設定します。|  
|[CTooltipManager::UpdateTooltips](../Topic/CTooltipManager::UpdateTooltips.md)||  
  
## 解説  
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、`CMFCToolTipInfo`、`CTooltipManager` を同時に使用し、カスタマイズされたツールヒントをアプリケーションに実装します。  これらのツールヒントのクラスを使用する方法の例については、[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) のトピックを参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## 必要条件  
 **ヘッダー:** afxtooltipmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)