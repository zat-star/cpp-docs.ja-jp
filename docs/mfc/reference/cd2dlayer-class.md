---
title: "CD2DLayer クラス | Microsoft Docs"
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
  - "afxrendertarget/CD2DLayer"
  - "CD2DLayer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLayer クラス"
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DLayer クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Layer のラッパー。  
  
## 構文  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DLayer::CD2DLayer](../Topic/CD2DLayer::CD2DLayer.md)|CD2DLayer オブジェクトを構築します。|  
|[CD2DLayer::~CD2DLayer](../Topic/CD2DLayer::~CD2DLayer.md)|デストラクターです。  D2D レイヤー オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DLayer::Attach](../Topic/CD2DLayer::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DLayer::Create](../Topic/CD2DLayer::Create.md)|CD2DLayer を作成します。  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DLayer::Destroy](../Topic/CD2DLayer::Destroy.md)|CD2DLayer オブジェクトを破棄します   \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) をオーバーライドします\)。|  
|[CD2DLayer::Detach](../Topic/CD2DLayer::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DLayer::Get](../Topic/CD2DLayer::Get.md)|ID2D1Layer インターフェイスを返します。|  
|[CD2DLayer::GetSize](../Topic/CD2DLayer::GetSize.md)|デバイスに依存しないピクセルで表されたレンダー ターゲットのサイズを返します。|  
|[CD2DLayer::IsValid](../Topic/CD2DLayer::IsValid.md)|リソースの有効性を検証します \([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) をオーバーライドします\)。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DLayer::operator ID2D1Layer\*](../Topic/CD2DLayer::operator%20ID2D1Layer*.md)|ID2D1Layer インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DLayer::m\_pLayer](../Topic/CD2DLayer::m_pLayer.md)|ID2D1Layer オブジェクトへのポインターを格納します。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DLayer](../../mfc/reference/cd2dlayer-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)