---
title: "CDynamicChain クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicChain クラス"
  - "チェイン (メッセージ マップを)"
  - "メッセージ マップ, チェーン"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDynamicChain クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、メッセージ マップの動的チェインをサポートするメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CDynamicChain  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|コンストラクターです。|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|別のオブジェクトのメッセージ マップに Windows メッセージを表示します。|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|コレクションからメッセージ マップのエントリを削除します。|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|メッセージ マップのエントリをコレクションに追加するか、既存のエントリを変更します。|  
  
## 解説  
 `CDynamicChain` には、メッセージ マップのコレクションを管理し、別のオブジェクトのメッセージ マップに、実行時にに指示する Windows メッセージを有効にします。  
  
 メッセージ マップの動的チェインのサポートを追加するには、次の操作を行います。:  
  
-   `CDynamicChain`からクラスを派生します。  メッセージ マップでは、別のオブジェクトの既定のメッセージ マップにチェーンするには [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) のマクロを指定します。  
  
-   、[CMessageMap](../../atl/reference/cmessagemap-class.md)からバインダーにチェーンするすべてのクラスを派生します。  `CMessageMap` は、オブジェクトが他のオブジェクトにメッセージ マップを公開するようにします。  
  
-   識別するに `CDynamicChain::SetChainEntry` を呼び出します。オブジェクトにメッセージ マップにチェーンする場合は、バインダー。  
  
 たとえば、次のように、クラスが定義されているとする:  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/CPP/cdynamicchain-class_1.h)]  
  
 クライアントは、`CMyWindow::SetChainEntry`を呼び出します:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/CPP/cdynamicchain-class_2.cpp)]  
  
 `chainedObj` がチェーン オブジェクトで、`CMessageMap`から派生したクラスのインスタンスです。  これで `myCtl` が `OnPaint` か `OnSetFocus`で処理されないメッセージを受信した場合、ウィンドウ プロシージャは `chainedObj` の既定のメッセージ マップにメッセージを表示します。  
  
 メッセージ マップのチェーンに関する詳細については、" "の「ATL ウィンドウ クラスを [&#91;メッセージ マップ&#93;](../../atl/message-maps-atl.md) 」。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [CWindowImpl クラス](../Topic/CWindowImpl%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)