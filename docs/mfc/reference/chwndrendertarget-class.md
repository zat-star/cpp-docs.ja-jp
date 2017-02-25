---
title: "CHwndRenderTarget クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHwndRenderTarget"
  - "afxrendertarget/CHwndRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHwndRenderTarget クラス"
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CHwndRenderTarget クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1HwndRenderTarget のラッパー。  
  
## 構文  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHwndRenderTarget::CHwndRenderTarget](../Topic/CHwndRenderTarget::CHwndRenderTarget.md)|HWND から CHwndRenderTarget オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHwndRenderTarget::Attach](../Topic/CHwndRenderTarget::Attach.md)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|  
|[CHwndRenderTarget::CheckWindowState](../Topic/CHwndRenderTarget::CheckWindowState.md)|このレンダー ターゲットに関連付けられている HWND が遮られているかどうかを示します。|  
|[CHwndRenderTarget::Create](../Topic/CHwndRenderTarget::Create.md)|ウィンドウに関連付けられているレンダー ターゲットを作成します。|  
|[CHwndRenderTarget::Detach](../Topic/CHwndRenderTarget::Detach.md)|レンダー ターゲット インターフェイスをオブジェクトからデタッチします。|  
|[CHwndRenderTarget::GetHwnd](../Topic/CHwndRenderTarget::GetHwnd.md)|このレンダー ターゲットに関連付けられている HWND を返します。|  
|[CHwndRenderTarget::GetHwndRenderTarget](../Topic/CHwndRenderTarget::GetHwndRenderTarget.md)|ID2D1HwndRenderTarget インターフェイスを返します。|  
|[CHwndRenderTarget::ReCreate](../Topic/CHwndRenderTarget::ReCreate.md)|ウィンドウに関連付けられているレンダー ターゲットを再作成します。|  
|[CHwndRenderTarget::Resize](../Topic/CHwndRenderTarget::Resize.md)|レンダー ターゲットのサイズを指定したピクセル サイズに変更します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget\*](../Topic/CHwndRenderTarget::operator%20ID2D1HwndRenderTarget*.md)|ID2D1HwndRenderTarget インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CHwndRenderTarget::m\_pHwndRenderTarget](../Topic/CHwndRenderTarget::m_pHwndRenderTarget.md)|ID2D1HwndRenderTarget オブジェクトへのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)