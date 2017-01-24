---
title: "CD2DPathGeometry クラス | Microsoft Docs"
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
  - "afxrendertarget/CD2DPathGeometry"
  - "CD2DPathGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DPathGeometry クラス"
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DPathGeometry クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1PathGeometry のラッパー。  
  
## 構文  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DPathGeometry::CD2DPathGeometry](../Topic/CD2DPathGeometry::CD2DPathGeometry.md)|CD2DPathGeometry オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DPathGeometry::Attach](../Topic/CD2DPathGeometry::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DPathGeometry::Create](../Topic/CD2DPathGeometry::Create.md)|CD2DPathGeometry を作成します。  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DPathGeometry::Destroy](../Topic/CD2DPathGeometry::Destroy.md)|CD2DPathGeometry オブジェクトを破棄します。  \([CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md) をオーバーライドします\)。|  
|[CD2DPathGeometry::Detach](../Topic/CD2DPathGeometry::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DPathGeometry::GetFigureCount](../Topic/CD2DPathGeometry::GetFigureCount.md)|パス ジオメトリ内の図の数を取得します。|  
|[CD2DPathGeometry::GetSegmentCount](../Topic/CD2DPathGeometry::GetSegmentCount.md)|パス ジオメトリ内の線分の数を取得します。|  
|[CD2DPathGeometry::Open](../Topic/CD2DPathGeometry::Open.md)|図と線分を持つパス ジオメトリの作成に使用されるジオメトリ シンクを取得します。|  
|[CD2DPathGeometry::Stream](../Topic/CD2DPathGeometry::Stream.md)|パス ジオメトリのコンテンツを、指定した ID2D1GeometrySink にコピーします。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DPathGeometry::m\_pPathGeometry](../Topic/CD2DPathGeometry::m_pPathGeometry.md)|ID2D1PathGeometry へのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DGeometry](../Topic/CD2DGeometry%20Class.md)  
  
 [CD2DPathGeometry](../../mfc/reference/cd2dpathgeometry-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)