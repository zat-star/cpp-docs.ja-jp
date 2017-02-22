---
title: "アニメーション コントロールの使い方 | Microsoft Docs"
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
  - "アニメーション コントロール [C++]"
  - "CAnimateCtrl クラス, アニメーション コントロール"
  - "コントロール [MFC], アニメーション"
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# アニメーション コントロールの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アニメーション コントロールの一般的な使用法がパターンに従います。:  
  
-   コントロールが作成されます。  コントロールをダイアログ ボックス テンプレートで指定されている場合、作成はダイアログ ボックスの作成時に自動的に行われます。ダイアログ クラスの [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) のメンバーがアニメーション コントロールに対応する必要があります。または、任意のウィンドウの子ウィンドウとしてコントロールを作成するために [作成](../Topic/CAnimateCtrl::Create.md) メンバー関数を使用できます。  
  
-   [開く](../Topic/CAnimateCtrl::Open.md) メンバー関数を呼び出してアニメーション コントロールに AVI クリップを読み込んでください。  アニメーション コントロールがダイアログ ボックス内にある場合、その適切な位置は、ダイアログ クラスの [OnInitDialog](../Topic/CDialog::OnInitDialog.md) 関数です。  
  
-   [再生](../Topic/CAnimateCtrl::Play.md) のメンバー関数を呼び出すことによってクリップをします。  アニメーション コントロールがダイアログ ボックス内にある場合、その適切な位置は、ダイアログ クラスの **OnInitDialog** 関数です。  **再生** を呼び出すと、アニメーション コントロールに設定されている `ACS_AUTOPLAY` のスタイルがある場合は必要ではありません。  
  
-   クリップの一部を表示したり、フレームによりフレームする場合は、`Seek` メンバー関数を使用します。  再生中のクリップを停止するには、`Stop` メンバー関数を使用します。  
  
-   コントロールを直ちに破棄しようとして **閉じる** のメンバー関数を呼び出して、メモリからクリップを削除します。  
  
-   アニメーション コントロールがダイアログ ボックス内にある場合、`CAnimateCtrl` オブジェクトは自動的に破棄されます。  そうでない場合、確認する必要があります `CAnimateCtrl` コントロールおよびオブジェクトの両方が適切に破棄することができます。  コントロールを破棄すると、自動的に AVI クリップを閉じます。  
  
## 参照  
 [CAnimateCtrl の使い方](../Topic/Using%20CAnimateCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)