---
title: "プログレス コントロールの操作 | Microsoft Docs"
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
  - "制御 (プログレス コントロールを)"
  - "CProgressCtrl クラス, 操作"
  - "CProgressCtrl クラス, 使用"
  - "CProgressCtrl クラス, 処理"
  - "プログレス コントロール [C++], 操作"
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プログレス コントロールの操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログレス コントロール \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) の現在の位置を変更するには、3 とおりの方法があります。  
  
-   位置はプリセット インクリメント量変更できます。  
  
-   位置は任意の量変更できます。  
  
-   位置、特定の値を変更できます。  
  
### 事前定義して位置を変更する必要がある。  
  
1.  インクリメント量を設定するために [SetStep](../Topic/CProgressCtrl::SetStep.md) メンバー関数を使用します。  既定値は 10 です。  この値は、コントロールの初期化の 1 文字として正常に設定されます。  ステップ値が負のです。  
  
2.  位置をインクリメントするには [StepIt](../Topic/CProgressCtrl::StepIt.md) メンバー関数を使用します。  これにより、コントロールがそれ自体を再描画します。  
  
    > [!NOTE]
    >  `StepIt` 位置をラップします。  たとえば、1 –100 の範囲を、手順 20 の場合、90 の位置は、`StepIt` 10.に位置を設定します。  
  
### 任意の量位置を変更するには  
  
1.  位置を変更するには [OffsetPos](../Topic/CProgressCtrl::OffsetPos.md) メンバー関数を使用します。  `OffsetPos` は 負の値を指定できます。  
  
    > [!NOTE]
    >  `OffsetPos`は、`StepIt`とは異なり、位置をラップしません。  新しい位置が範囲内になるように調整されます。  
  
### 位置を特定の値に変更するには  
  
1.  特定の位置に値を設定するには [SetPos](../Topic/CProgressCtrl::SetPos.md) メンバー関数を使用します。  必要に応じて、新しい位置が範囲内になるように調整されます。  
  
 通常、プログレス コントロールは出力のためだけに使用されます。  新しい値を指定せずに現在位置を取得するには、[GetPos](../Topic/CProgressCtrl::GetPos.md)を使用します。  
  
## 参照  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)   
 [コントロール](../mfc/controls-mfc.md)