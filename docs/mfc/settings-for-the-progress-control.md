---
title: "プログレス コントロールの設定 | Microsoft Docs"
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
  - "CProgressCtrl クラス, 設定"
  - "プログレス コントロール [C++], 設定"
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# プログレス コントロールの設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログレス コントロール \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) の基本設定は、範囲と現在位置です。  範囲は操作全体を表します。  現在位置をアプリケーションが処理の完了に向けたチームの進行状況を表します。  範囲または位置の原因に変更自体を再描画するプログレス コントロール。  
  
 既定では 0 – 100 に、範囲設定され、初期位置は 0 に設定されます。  プログレス コントロールの現在のスコープの設定を取得するには、[GetRange](../Topic/CProgressCtrl::GetRange.md) メンバー関数を使用します。  範囲を変更するには、[SetRange](../Topic/CProgressCtrl::SetRange.md) メンバー関数を使用します。  
  
 位置を設定するには、[SetPos](../Topic/CProgressCtrl::SetPos.md)を使用します。  新しい値を指定せずに現在位置を取得するには、[GetPos](../Topic/CProgressCtrl::GetPos.md)を使用します。  たとえば、現在のアクションの状態に問い合わせることがあります。  
  
 現在位置プログレス コントロールのステップ実行するには、[StepIt](../Topic/CProgressCtrl::StepIt.md)を使用します。  各ステップの量を設定するには、[SetStep](../Topic/CProgressCtrl::SetStep.md)を使用します。  
  
## 参照  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)   
 [コントロール](../mfc/controls-mfc.md)