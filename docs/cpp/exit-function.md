---
title: "exit 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit 関数"
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# exit 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準インクルード ファイルの STDLIB.H で宣言された **exit** 関数は、C\+\+ プログラムを終了します。  
  
 **exit** の引数として指定された値は、プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。  慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。  
  
> [!NOTE]
>  STDLIB.H で定義された定数 `EXIT_FAILURE` および `EXIT_SUCCESS` を使用して、プログラムの成功または失敗を示すことができます。  
  
 **main** 関数から `return` ステートメントを発行することは、戻り値を引数として **exit** 関数を呼び出すことと同じです。  
  
 詳細については、『ランタイム ライブラリ リファレンス』の「[exit](../c-runtime-library/reference/exit-exit-exit.md)」を参照してください。  
  
## 参照  
 [プログラムの終了](../Topic/Program%20Termination.md)