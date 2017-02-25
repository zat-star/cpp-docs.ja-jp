---
title: "CDrawingManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDrawingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDrawingManager クラス"
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CDrawingManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDrawingManager` クラスは複雑な描画アルゴリズムを実装します。  
  
## 構文  
  
```  
class CDrawingManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDrawingManager::CDrawingManager](../Topic/CDrawingManager::CDrawingManager.md)|`CDrawingManager` オブジェクトを構築します。|  
|`CDrawingManager::~CDrawingManager`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDrawingManager::CreateBitmap\_32](../Topic/CDrawingManager::CreateBitmap_32.md)|アプリケーションが直接書き込める、32 ビットのデバイスに依存しないビットマップ \(DIB: Device\-Independent Bitmap\) を作成します。|  
|[CDrawingManager::DrawAlpha](../Topic/CDrawingManager::DrawAlpha.md)|透明または半透明のピクセルがあるビットマップを表示します。|  
|[CDrawingManager::DrawRotated](../Topic/CDrawingManager::DrawRotated.md)|指定された四角形の内部のソース DC コンテンツを \+\/\- 90°回転します。|  
|[CDrawingManager::DrawEllipse](../Topic/CDrawingManager::DrawEllipse.md)|指定された塗りつぶしと境界線の色で楕円を描画します。|  
|[CDrawingManager::DrawGradientRing](../Topic/CDrawingManager::DrawGradientRing.md)|リングを描画し、それを色のグラデーションで塗りつぶします。|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](../Topic/CDrawingManager::DrawLine,%20CDrawingManager::DrawLineA.md)|直線を描画します。|  
|[CDrawingManager::DrawRect](../Topic/CDrawingManager::DrawRect.md)|指定された塗りつぶしと境界線の色で四角形を描画します。|  
|[CDrawingManager::DrawShadow](../Topic/CDrawingManager::DrawShadow.md)|四角形領域に影を描画します。|  
|[CDrawingManager::Fill4ColorsGradient](../Topic/CDrawingManager::Fill4ColorsGradient.md)|2 色のグラデーションで四角形領域を塗りつぶします。|  
|[CDrawingManager::FillGradient](../Topic/CDrawingManager::FillGradient.md)|指定した色のグラデーションで四角形領域を塗りつぶします。|  
|[CDrawingManager::FillGradient2](../Topic/CDrawingManager::FillGradient2.md)|指定した色のグラデーションで四角形領域を塗りつぶします。  グラデーションの色の変更の報告も指定されます。|  
|[CDrawingManager::GrayRect](../Topic/CDrawingManager::GrayRect.md)|指定した灰色で四角形を塗りつぶします。|  
|[CDrawingManager::HighlightRect](../Topic/CDrawingManager::HighlightRect.md)|四角形領域を強調表示します。|  
|[CDrawingManager::HLStoRGB\_ONE](../Topic/CDrawingManager::HLStoRGB_ONE.md)|色を HLS 表現から RGB 表現に変換します。|  
|[CDrawingManager::HLStoRGB\_TWO](../Topic/CDrawingManager::HLStoRGB_TWO.md)|色を HLS 表現から RGB 表現に変換します。|  
|[CDrawingManager::HSVtoRGB](../Topic/CDrawingManager::HSVtoRGB.md)|色を HSV 表現から RGB 表現に変換します。|  
|[CDrawingManager::HuetoRGB](../Topic/CDrawingManager::HuetoRGB.md)|色合いの値を、赤、緑、青の各要素に変換するヘルパー メソッド。|  
|[CDrawingManager::MirrorRect](../Topic/CDrawingManager::MirrorRect.md)|四角形領域を反転させます。|  
|[CDrawingManager::PixelAlpha](../Topic/CDrawingManager::PixelAlpha.md)|半透明ピクセルの最終的な色を決定するヘルパー メソッド。|  
|[CDrawingManager::PrepareShadowMask](../Topic/CDrawingManager::PrepareShadowMask.md)|シャドウとして使用できるビットマップを作成します。|  
|[CDrawingManager::RGBtoHSL](../Topic/CDrawingManager::RGBtoHSL.md)|色を RGB 表現から HSL 表現に変換します。|  
|[CDrawingManager::RGBtoHSV](../Topic/CDrawingManager::RGBtoHSV.md)|色を RGB 表現から HSV 表現に変換します。|  
|[CDrawingManager::SetAlphaPixel](../Topic/CDrawingManager::SetAlphaPixel.md)|ビットマップ中の部分的に透明なピクセルに色を付けるヘルパー メソッド。|  
|[CDrawingManager::SetPixel](../Topic/CDrawingManager::SetPixel.md)|ビットマップ中の単一ピクセルを、指定された色に変更するヘルパー メソッド。|  
|[CDrawingManager::SmartMixColors](../Topic/CDrawingManager::SmartMixColors.md)|2 つの色を、重み付け比率を基に組み合わせます。|  
  
## 解説  
 `CDrawingManager` クラスには、影、色のグラデーション、および強調表示された四角形を描画する関数があります。  また、アルファ ブレンドも実行します。  このクラスを使用して、アプリケーションの UI を直接変更できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdrawmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)