---
title: "CD2DBrush クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBrush"
  - "afxrendertarget/CD2DBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBrush クラス"
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBrush クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Brush のラッパー。  
  
## 構文  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DBrush::CD2DBrush](../Topic/CD2DBrush::CD2DBrush.md)|CD2DBrush オブジェクトを構築します。|  
|[CD2DBrush::~CD2DBrush](../Topic/CD2DBrush::~CD2DBrush.md)|デストラクターです。  D2D ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DBrush::Attach](../Topic/CD2DBrush::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md)|CD2DBrush オブジェクトを破棄します。  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) をオーバーライドします\)。|  
|[CD2DBrush::Detach](../Topic/CD2DBrush::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DBrush::Get](../Topic/CD2DBrush::Get.md)|ID2D1Brush インターフェイスを返します。|  
|[CD2DBrush::GetOpacity](../Topic/CD2DBrush::GetOpacity.md)|このブラシの不透明度を取得します。|  
|[CD2DBrush::GetTransform](../Topic/CD2DBrush::GetTransform.md)|レンダー ターゲットの現在の変換を取得します。|  
|[CD2DBrush::IsValid](../Topic/CD2DBrush::IsValid.md)|リソースの有効性を検証します \([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) をオーバーライドします\)。|  
|[CD2DBrush::SetOpacity](../Topic/CD2DBrush::SetOpacity.md)|このブラシの不透明度を設定します。|  
|[CD2DBrush::SetTransform](../Topic/CD2DBrush::SetTransform.md)|指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。  以降の描画操作はすべて、変換された空間で行われます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DBrush::operator ID2D1Brush\*](../Topic/CD2DBrush::operator%20ID2D1Brush*.md)|ID2D1Brush インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DBrush::m\_pBrush](../Topic/CD2DBrush::m_pBrush.md)|ID2D1Brush オブジェクトへのポインターを格納します。|  
|[CD2DBrush::m\_pBrushProperties](../Topic/CD2DBrush::m_pBrushProperties.md)|ブラシのプロパティ。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)