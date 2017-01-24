---
title: "CMFCToolTipInfo クラス | Microsoft Docs"
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
  - "CMFCToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipInfo クラス"
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolTipInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ツールヒントの外観に関する情報を格納します。  
  
## 構文  
  
```  
class CMFCToolTipInfo  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolTipInfo::operator\=](../Topic/CMFCToolTipInfo::operator=.md)||  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolTipInfo::m\_bBalloonTooltip](../Topic/CMFCToolTipInfo::m_bBalloonTooltip.md)|ツールヒントの外観をバルーンにするかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bBoldLabel](../Topic/CMFCToolTipInfo::m_bBoldLabel.md)|ツールヒントのラベルを太字のフォントで表示するかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bDrawDescription](../Topic/CMFCToolTipInfo::m_bDrawDescription.md)|ツールヒントに説明を含めるかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bDrawIcon](../Topic/CMFCToolTipInfo::m_bDrawIcon.md)|ツールヒントにアイコンを含めるかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bDrawSeparator](../Topic/CMFCToolTipInfo::m_bDrawSeparator.md)|ツールヒントのラベルとツールヒントの説明の間に区切り記号を表示するかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bRoundedCorners](../Topic/CMFCToolTipInfo::m_bRoundedCorners.md)|ツールヒントの角を丸くするかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m\_bVislManagerTheme](../Topic/CMFCToolTipInfo::m_bVislManagerTheme.md)|ツールヒントの外観をビジュアル マネージャーで制御する必要があるかどうかを示すブール値変数 \(「[CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)」を参照してください\)。|  
|[CMFCToolTipInfo::m\_clrBorder](../Topic/CMFCToolTipInfo::m_clrBorder.md)|ツールヒントの境界線の色。|  
|[CMFCToolTipInfo::m\_clrFill](../Topic/CMFCToolTipInfo::m_clrFill.md)|ツールヒントの背景の色。|  
|[CMFCToolTipInfo::m\_clrFillGradient](../Topic/CMFCToolTipInfo::m_clrFillGradient.md)|ツールヒントのグラデーション塗りの色。|  
|[CMFCToolTipInfo::m\_clrText](../Topic/CMFCToolTipInfo::m_clrText.md)|ツールヒントのテキストの色。|  
|[CMFCToolTipInfo::m\_nGradientAngle](../Topic/CMFCToolTipInfo::m_nGradientAngle.md)|ツールヒントのグラデーション塗りの角度。|  
|[CMFCToolTipInfo::m\_nMaxDescrWidth](../Topic/CMFCToolTipInfo::m_nMaxDescrWidth.md)|ツールヒントの説明で可能な最大幅 \(ピクセル\)。|  
  
## 解説  
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、`CMFCToolTipInfo`、[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md) を同時に使用し、カスタマイズされたツールヒントをアプリケーションに実装します。  これらのツールヒントのクラスを使用する方法の例については、[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) のトピックを参照してください。  
  
## 使用例  
 次の例では、`CMFCToolTipInfo` クラスのさまざまなメンバー変数の値を設定する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/CPP/cmfctooltipinfo-class_1.cpp)]  
  
## 継承階層  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## 必要条件  
 **ヘッダー:** afxtooltipctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)