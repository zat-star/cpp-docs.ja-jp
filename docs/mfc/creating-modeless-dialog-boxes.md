---
title: "モードレス ダイアログ ボックスの作成 | Microsoft Docs"
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
  - "MFC ダイアログ ボックス, 作成"
  - "MFC ダイアログ ボックス, モードレス"
  - "モードレス ダイアログ ボックス, 作成"
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# モードレス ダイアログ ボックスの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モードレス ダイアログ ボックスでは、ダイアログ クラスのパブリック コンストラクターを持つ必要があります。  モードレス ダイアログ ボックスを作成するには、パブリック コンストラクターを呼び出し、次にダイアログ リソースを読み込むようにダイアログ オブジェクトの [作成](../Topic/CDialog::Create.md) メンバー関数を呼び出します。  コンストラクターの呼び出し中または後に **作成** のいずれかを呼び出すことができます。  ダイアログ リソースに **WS\_VISIBLE**プロパティがある場合は、ダイアログ ボックスが反映されます。  そうでない場合は、[ShowWindow](../Topic/CWnd::ShowWindow.md) メンバー関数を呼び出す必要があります。  
  
## 参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)