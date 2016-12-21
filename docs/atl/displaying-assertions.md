---
title: "アサーションの表示 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アサーション, デバッグ"
  - "アサーション, 表示"
  - "デバッグ [ATL], 表示 (アサーションを)"
  - "デバッグ (アサーションを)"
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アサーションの表示
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

目的のサービスに接続するクライアントが応答しなくなったように見えるサービスが見られないするメッセージ ボックスを保持し、表示されることがあります。  コードをデバッグするには、Visual C\+\+ デバッガーの使用によって、これを検証できます \(このセクションの [タスク マネージャーを使用する](../atl/using-task-manager.md) を"を参照してください\)。  
  
 このサービスは、参照できないメッセージ ボックスを表示していると判断した場合は、サービスを使用する前に **Allow Service to Interact with Desktop** オプションを設定することもできます。  このオプションは、デスクトップに表示されるようにサービスを表示するメッセージ ボックスを使用すると、開始のパラメーターです。  このオプションを設定するには、サービスのコントロール パネルのアプリケーションを開き、サービスを選択し、**\[スタートアップ\]**をクリックし、を **Allow Service to Interact with Desktop** のオプションを選択します。  
  
## 参照  
 [デバッグのヒント](../atl/debugging-tips.md)