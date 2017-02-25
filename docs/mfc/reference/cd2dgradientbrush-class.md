---
title: "CD2DGradientBrush クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DGradientBrush"
  - "afxrendertarget/CD2DGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGradientBrush クラス"
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DGradientBrush クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CD2DLinearGradientBrush クラスおよび CD2DRadialGradientBrush クラスの基本クラス。  
  
## 構文  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DGradientBrush::CD2DGradientBrush](../Topic/CD2DGradientBrush::CD2DGradientBrush.md)|CD2DGradientBrush オブジェクトを構築します。|  
|[CD2DGradientBrush::~CD2DGradientBrush](../Topic/CD2DGradientBrush::~CD2DGradientBrush.md)|デストラクターです。  D2D グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md)|CD2DGradientBrush オブジェクトを破棄します   \([CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md) をオーバーライドします\)。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DGradientBrush::m\_arGradientStops](../Topic/CD2DGradientBrush::m_arGradientStops.md)|D2D1\_GRADIENT\_STOP 構造体の配列。|  
|[CD2DGradientBrush::m\_colorInterpolationGamma](../Topic/CD2DGradientBrush::m_colorInterpolationGamma.md)|グラデーション境界間の色補間を実行する領域。|  
|[CD2DGradientBrush::m\_extendMode](../Topic/CD2DGradientBrush::m_extendMode.md)|正規化された範囲 \[0,1\] に含まれていないグラデーションの動作。|  
|[CD2DGradientBrush::m\_pGradientStops](../Topic/CD2DGradientBrush::m_pGradientStops.md)|D2D1\_GRADIENT\_STOP 構造体の配列へのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)