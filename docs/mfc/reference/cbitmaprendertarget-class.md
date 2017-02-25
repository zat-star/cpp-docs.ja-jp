---
title: "CBitmapRenderTarget クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CBitmapRenderTarget"
  - "CBitmapRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmapRenderTarget クラス"
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CBitmapRenderTarget クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1BitmapRenderTarget のラッパー。  
  
## 構文  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](../Topic/CBitmapRenderTarget::CBitmapRenderTarget.md)|CBitmapRenderTarget オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBitmapRenderTarget::Attach](../Topic/CBitmapRenderTarget::Attach.md)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|  
|[CBitmapRenderTarget::Detach](../Topic/CBitmapRenderTarget::Detach.md)|レンダー ターゲット インターフェイスをオブジェクトからデタッチします。|  
|[CBitmapRenderTarget::GetBitmap](../Topic/CBitmapRenderTarget::GetBitmap.md)|このレンダー ターゲットのビットマップを取得します。  返されたビットマップは描画操作に使用できます。|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](../Topic/CBitmapRenderTarget::GetBitmapRenderTarget.md)|ID2D1BitmapRenderTarget インターフェイスを返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget\*](../Topic/CBitmapRenderTarget::operator%20ID2D1BitmapRenderTarget*.md)|ID2D1BitmapRenderTarget インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CBitmapRenderTarget::m\_pBitmapRenderTarget](../Topic/CBitmapRenderTarget::m_pBitmapRenderTarget.md)|ID2D1BitmapRenderTarget オブジェクトへのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CBitmapRenderTarget](../../mfc/reference/cbitmaprendertarget-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)