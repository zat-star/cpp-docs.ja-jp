---
title: "モーダル ダイアログ ボックスの作成 | Microsoft Docs"
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
  - "MFC ダイアログ ボックス, モーダル"
  - "モーダル ダイアログ ボックス, 作成"
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# モーダル ダイアログ ボックスの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モーダル ダイアログ ボックスを作成するには、[CDialog](../mfc/reference/cdialog-class.md)で宣言された 2 個のパブリック コンストラクターのいずれかを呼び出します。  次に、ユーザーがキャンセルをクリックするまで、ダイアログ ボックスを表示して、その相互作用を管理するダイアログ オブジェクトの [DoModal](../Topic/CDialog::DoModal.md) メンバー関数を呼び出します。  `DoModal` してこの管理は、ダイアログ ボックスのモーダルを行うメソッドです。  モーダル ダイアログ ボックスでは、`DoModal` はダイアログ リソースを読み込みます。  
  
## 参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)