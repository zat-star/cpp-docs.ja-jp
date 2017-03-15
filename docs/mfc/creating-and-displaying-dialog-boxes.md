---
title: "ダイアログ ボックスの作成と表示 | Microsoft Docs"
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
  - "MFC ダイアログ ボックス, 作成"
  - "MFC ダイアログ ボックス, 表示"
  - "モーダル ダイアログ ボックス, 作成"
  - "モードレス ダイアログ ボックス, 作成"
  - "開く (ダイアログ ボックスを)"
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ダイアログ ボックスの作成と表示
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ オブジェクトを作成することは、記述し操作です。  まず、ダイアログ オブジェクトを構築し、ダイアログ ウィンドウを作成します。  モーダルおよびモードレス ダイアログ ボックスは、を作成および表示する処理が多少異なります。  モーダルおよびモードレス ダイアログ ボックスがどのように作成され、通常表示されるかを次の表に示します。  
  
### ダイアログ ボックスの作成  
  
|ダイアログの型|アプリケーションを作成する方法|  
|-------------|---------------------|  
|[モードレス](../mfc/creating-modeless-dialog-boxes.md)|`CDialog`を構築し、**作成** メンバー関数を呼び出します。|  
|[モーダル](../mfc/creating-modal-dialog-boxes.md)|構造 `CDialog`は、`DoModal` メンバー関数を呼び出します。|  
  
 必要に応じて、作成し、ダイアログ テンプレート リソースではなく、構築 [インメモリ ダイアログ テンプレート](../mfc/using-a-dialog-template-in-memory.md) からダイアログ ボックスがあります。  ただし、高度なトピックです。  
  
## 参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)