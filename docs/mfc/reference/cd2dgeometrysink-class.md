---
title: "CD2DGeometrySink クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DGeometrySink"
  - "CD2DGeometrySink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometrySink クラス"
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DGeometrySink クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1GeometrySink のラッパー。  
  
## 構文  
  
```  
class CD2DGeometrySink;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DGeometrySink::CD2DGeometrySink](../Topic/CD2DGeometrySink::CD2DGeometrySink.md)|CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。|  
|[CD2DGeometrySink::~CD2DGeometrySink](../Topic/CD2DGeometrySink::~CD2DGeometrySink.md)|デストラクターです。  D2D ジオメトリ シンク オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DGeometrySink::AddArc](../Topic/CD2DGeometrySink::AddArc.md)|1 つの円弧をパス ジオメトリに追加します。|  
|[CD2DGeometrySink::AddBezier](../Topic/CD2DGeometrySink::AddBezier.md)|現在の点と指定した終点の間に 3 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddBeziers](../Topic/CD2DGeometrySink::AddBeziers.md)|一連の 3 次ベジエ曲線を作成し、ジオメトリ シンクに追加します。|  
|[CD2DGeometrySink::AddLine](../Topic/CD2DGeometrySink::AddLine.md)|現在の点と指定した終点の間に線分を作成し、ジオメトリ シンクに追加します。|  
|[CD2DGeometrySink::AddLines](../Topic/CD2DGeometrySink::AddLines.md)|指定された点を使用して一連の直線を作成し、ジオメトリ シンクに追加します。|  
|[CD2DGeometrySink::AddQuadraticBezier](../Topic/CD2DGeometrySink::AddQuadraticBezier.md)|現在の点と指定した終点の間に 2 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddQuadraticBeziers](../Topic/CD2DGeometrySink::AddQuadraticBeziers.md)|単一の呼び出しで、一連の 2 次ベジエ セグメントを配列として追加します。|  
|[CD2DGeometrySink::BeginFigure](../Topic/CD2DGeometrySink::BeginFigure.md)|指定した点から新しい図形を開始します。|  
|[CD2DGeometrySink::Close](../Topic/CD2DGeometrySink::Close.md)|ジオメトリ シンクを閉じます。|  
|[CD2DGeometrySink::EndFigure](../Topic/CD2DGeometrySink::EndFigure.md)|現在の図形を終了します。必要に応じて、図形を閉じます。|  
|[CD2DGeometrySink::Get](../Topic/CD2DGeometrySink::Get.md)|ID2D1GeometrySink インターフェイスを返します。|  
|[CD2DGeometrySink::IsValid](../Topic/CD2DGeometrySink::IsValid.md)|ジオメトリ シンクの有効性を検証します。|  
|[CD2DGeometrySink::SetFillMode](../Topic/CD2DGeometrySink::SetFillMode.md)|このジオメトリ シンクによって記述されたジオメトリの内部にある点と外部にある点を判別するために使用するメソッドを指定します。|  
|[CD2DGeometrySink::SetSegmentFlags](../Topic/CD2DGeometrySink::SetSegmentFlags.md)|ジオメトリ シンクに追加する新しいセグメントに適用するストローク オプションと結合オプションを指定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink\*](../Topic/CD2DGeometrySink::operator%20ID2D1GeometrySink*.md)|ID2D1GeometrySink インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DGeometrySink::m\_pSink](../Topic/CD2DGeometrySink::m_pSink.md)|ID2D1GeometrySink へのポインター。|  
  
## 継承階層  
 [CD2DGeometrySink](../../mfc/reference/cd2dgeometrysink-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)