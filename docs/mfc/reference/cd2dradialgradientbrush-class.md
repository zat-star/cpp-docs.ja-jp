---
title: "CD2DRadialGradientBrush クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DRadialGradientBrush"
  - "afxrendertarget/CD2DRadialGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRadialGradientBrush クラス"
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DRadialGradientBrush クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1RadialGradientBrush のラッパー。  
  
## 構文  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](../Topic/CD2DRadialGradientBrush::CD2DRadialGradientBrush.md)|CD2DLinearGradientBrush オブジェクトを構築します。|  
|[CD2DRadialGradientBrush::~CD2DRadialGradientBrush](../Topic/CD2DRadialGradientBrush::~CD2DRadialGradientBrush.md)|デストラクターです。  D2D 放射状グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DRadialGradientBrush::Attach](../Topic/CD2DRadialGradientBrush::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DRadialGradientBrush::Create](../Topic/CD2DRadialGradientBrush::Create.md)|CD2DRadialGradientBrush を作成します   \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DRadialGradientBrush::Destroy](../Topic/CD2DRadialGradientBrush::Destroy.md)|CD2DRadialGradientBrush オブジェクトを破棄します。  \([CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md) オーバーライドします\)。|  
|[CD2DRadialGradientBrush::Detach](../Topic/CD2DRadialGradientBrush::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DRadialGradientBrush::Get](../Topic/CD2DRadialGradientBrush::Get.md)|ID2D1RadialGradientBrush インターフェイスを返します。|  
|[CD2DRadialGradientBrush::GetCenter](../Topic/CD2DRadialGradientBrush::GetCenter.md)|グラデーションの楕円の中心点を取得します。|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](../Topic/CD2DRadialGradientBrush::GetGradientOriginOffset.md)|グラデーションの楕円の中心点からのグラデーションの原点のオフセットを取得します。|  
|[CD2DRadialGradientBrush::GetRadiusX](../Topic/CD2DRadialGradientBrush::GetRadiusX.md)|グラデーションの楕円の x 半径を取得します。|  
|[CD2DRadialGradientBrush::GetRadiusY](../Topic/CD2DRadialGradientBrush::GetRadiusY.md)|グラデーションの楕円の y 半径を取得します。|  
|[CD2DRadialGradientBrush::SetCenter](../Topic/CD2DRadialGradientBrush::SetCenter.md)|ブラシの座標空間におけるグラデーションの楕円の中心点を指定します。|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](../Topic/CD2DRadialGradientBrush::SetGradientOriginOffset.md)|グラデーションの楕円の中心点からのグラデーションの原点のオフセットを指定します。|  
|[CD2DRadialGradientBrush::SetRadiusX](../Topic/CD2DRadialGradientBrush::SetRadiusX.md)|ブラシの座標空間におけるグラデーションの楕円の x 半径を指定します。|  
|[CD2DRadialGradientBrush::SetRadiusY](../Topic/CD2DRadialGradientBrush::SetRadiusY.md)|ブラシの座標空間におけるグラデーションの楕円の y 半径を指定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush\*](../Topic/CD2DRadialGradientBrush::operator%20ID2D1RadialGradientBrush*.md)|ID2D1RadialGradientBrush インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DRadialGradientBrush::m\_pRadialGradientBrush](../Topic/CD2DRadialGradientBrush::m_pRadialGradientBrush.md)|ID2D1RadialGradientBrush へのポインター。|  
|[CD2DRadialGradientBrush::m\_RadialGradientBrushProperties](../Topic/CD2DRadialGradientBrush::m_RadialGradientBrushProperties.md)|ブラシのグラデーションの中心点、グラデーションの原点のオフセット、および x 半径と y 半径。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 [CD2DRadialGradientBrush](../../mfc/reference/cd2dradialgradientbrush-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)