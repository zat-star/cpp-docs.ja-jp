---
title: "MFC のカスタマイズ | Microsoft Docs"
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
  - "カスタマイズ, MFC の拡張"
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
caps.latest.revision: 21
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC のカスタマイズ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、MFC アプリケーションをカスタマイズするためのヒントを示します。  
  
## 全般的なカスタマイズ  
 アプリケーションの状態をレジストリに保存して読み込むことができます。  このオプションを有効にすると、アプリケーションはレジストリから初期状態を読み込みます。  アプリケーションの初期ドッキング レイアウトを変更した場合、アプリケーションのレジストリ データをクリアする必要があります。  クリアしないと、初期レイアウトに加えた変更内容がレジストリ内のデータによってオーバーライドされます。  
  
## クラス固有のカスタマイズ  
 カスタマイズの詳細なヒントについては、以下のトピックを参照してください。  
  
-   [CBasePane クラス](../mfc/reference/cbasepane-class.md)  
  
-   [CDockablePane クラス](../Topic/CDockablePane%20Class.md)  
  
-   [CDockingManager クラス](../mfc/reference/cdockingmanager-class.md)  
  
-   [CMFCBaseTabCtrl クラス](../mfc/reference/cmfcbasetabctrl-class.md)  
  
## その他のカスタマイズのヒント  
 [キーボードとマウスのカスタマイズ](../mfc/keyboard-and-mouse-customization.md)  
  
 [ユーザー定義のツール](../Topic/User-defined%20Tools.md)  
  
## 参照  
 [MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)   
 [カスタマイズによるセキュリティへの影響](../Topic/Security%20Implications%20of%20Customization.md)