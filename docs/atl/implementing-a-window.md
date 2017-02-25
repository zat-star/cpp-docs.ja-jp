---
title: "ウィンドウの実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, ウィンドウ"
  - "CWindowImpl クラス, 使用"
  - "ウィンドウ [C++], 実装 (ATL で)"
ms.assetid: eb1ce8d6-72f9-4894-aae7-e60a61665628
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ウィンドウの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスは [CWindowImpl](../Topic/CWindowImpl%20Class.md) ウィンドウを実装し、メッセージを処理できるようにします。  ATL で渡すメッセージは、メッセージ マップに基づいています。  ここでは示しています:  
  
-   のコントロールへの [メッセージ ハンドラーを追加します。](../atl/adding-an-atl-message-handler.md) します。  
  
-   どの [メッセージ マップ](../atl/message-maps-atl.md) と、その使用方法を確認する。  
  
-   [メッセージ ハンドラー関数](../atl/message-handler-functions.md)の構文。  
  
-   どのように [CWindowImpl のウィンドウを実装します。](../atl/implementing-a-window-with-cwindowimpl.md)。  
  
## 参照  
 [ウィンドウ クラス](../Topic/ATL%20Window%20Classes.md)