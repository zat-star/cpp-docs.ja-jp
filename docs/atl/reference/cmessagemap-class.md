---
title: "CMessageMap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMessageMap"
  - "ATL.CMessageMap"
  - "ATL::CMessageMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, メッセージ ハンドラー"
  - "CMessageMap クラス"
  - "メッセージ マップ, ATL"
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMessageMap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、オブジェクトのメッセージ マップに別のオブジェクトにアクセスするようにします。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class ATL_NO_VTABLE CMessageMap  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMessageMap::ProcessWindowMessage](../Topic/CMessageMap::ProcessWindowMessage.md)|`CMessageMap`のメッセージ マップ派生クラスにアクセスします。|  
  
## 解説  
 `CMessageMap` は、オブジェクトのメッセージ マップに別のオブジェクトにアクセスできるようにする抽象基本クラスです。  メッセージ マップを公開するオブジェクトのクラスは `CMessageMap`から派生する必要があります。  
  
 ATL を使用 `CMessageMap` 含まれているウィンドウをサポートすると動的メッセージはチェーンをマップします。  たとえば、`CMessageMap`から [CContainedWindow](../Topic/CContainedWindowT%20Class.md) のオブジェクトを含むを取得する必要があります。並べ替えます。  次のコードは [SUBEDIT](../../top/visual-cpp-samples.md) の例から取得されます。  [CComControl](../../atl/reference/ccomcontrol-class.md)によって、`CAtlEdit` のクラスは `CMessageMap`から自動的に取得します。  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/CPP/cmessagemap-class_1.h)]  
  
 含まれているウィンドウ、`m_EditCtrl`を含むクラスで、メッセージ マップを使用するため、`CAtlEdit` は `CMessageMap`から取得します。  
  
 メッセージ マップに関する詳細については、" "の「ATL ウィンドウ クラスを [&#91;メッセージ マップ&#93;](../../atl/message-maps-atl.md) 」。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [CDynamicChain クラス](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)   
 [クラスの概要](../../atl/atl-class-overview.md)