---
title: "反映されたメッセージの処理方法 | Microsoft Docs"
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
  - "メッセージ処理, リフレクション メッセージ"
  - "リフレクション メッセージ, 処理"
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 反映されたメッセージの処理方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メッセージ リフレクションはコントロールのメッセージは、コントロール自体の `WM_CTLCOLOR`、**WM\_COMMAND**と **WM\_NOTIFY**など\) を処理することができます。  これは、コントロールを独立したおよび Portable になります。  Windows コモン コントロールを使用して、ActiveX コントロールの機能の使用 \(以前の OLE コントロールとも呼ばれます\)。  
  
 メッセージ リフレクションは `CWnd`\-派生クラス\) を簡単に再利用できるようになります。  メッセージ リフレクションは **ON\_XXX\_REFLECT** の特別なメッセージ マップのエントリを使用して [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)で、機能: たとえば、**ON\_CTLCOLOR\_REFLECT** と **ON\_CONTROL\_REFLECT**。  [テクニカル ノート 62](../mfc/tn062-message-reflection-for-windows-controls.md) は メッセージ リフレクションを詳しく説明します。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [メッセージ リフレクションについて理解を深める。](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [コモン コントロールのメッセージ リフレクションを実装してください。](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX コントロールのメッセージ リフレクションを実装してください。](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## 参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)