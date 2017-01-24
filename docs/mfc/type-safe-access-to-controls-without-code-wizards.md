---
title: "コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス | Microsoft Docs"
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
  - "ダイアログ ボックス コントロール, アクセス"
  - "ダイアログ ボックス, アクセス (コントロールに)"
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールへのタイプ セーフ アクセスを作成するための最初のアプローチは次の例のように、適切な C\+\+ コントロール型にクラスの `CWnd``GetDlgItem` のメンバー関数の戻り値の型を、キャストするためにインライン メンバー関数を使用します:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 次のようなコードのタイプ セーフな方法でコントロールにアクセスするには、このメンバー関数を使用する:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## 参照  
 [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../Topic/Type-Safe%20Access%20to%20Controls%20in%20a%20Dialog%20Box.md)   
 [コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-with-code-wizards.md)