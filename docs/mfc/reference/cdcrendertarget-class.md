---
title: "CDCRenderTarget クラス | Microsoft Docs"
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
  - "afxrendertarget/CDCRenderTarget"
  - "CDCRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDCRenderTarget クラス"
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDCRenderTarget クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1DCRenderTarget のラッパー。  
  
## 構文  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDCRenderTarget::CDCRenderTarget](../Topic/CDCRenderTarget::CDCRenderTarget.md)|CDCRenderTarget オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDCRenderTarget::Attach](../Topic/CDCRenderTarget::Attach.md)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|  
|[CDCRenderTarget::BindDC](../Topic/CDCRenderTarget::BindDC.md)|描画コマンドの発行先のデバイス コンテキストにレンダー ターゲットをバインドします。|  
|[CDCRenderTarget::Create](../Topic/CDCRenderTarget::Create.md)|CDCRenderTarget を作成します。|  
|[CDCRenderTarget::Detach](../Topic/CDCRenderTarget::Detach.md)|レンダー ターゲット インターフェイスをオブジェクトからデタッチします。|  
|[CDCRenderTarget::GetDCRenderTarget](../Topic/CDCRenderTarget::GetDCRenderTarget.md)|ID2D1DCRenderTarget インターフェイスを返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget\*](../Topic/CDCRenderTarget::operator%20ID2D1DCRenderTarget*.md)|ID2D1DCRenderTarget インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDCRenderTarget::m\_pDCRenderTarget](../Topic/CDCRenderTarget::m_pDCRenderTarget.md)|ID2D1DCRenderTarget オブジェクトへのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)