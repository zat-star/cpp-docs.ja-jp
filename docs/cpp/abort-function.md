---
title: "abort 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort 関数"
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# abort 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準インクルード ファイルの STDLIB.H で宣言された **abort** 関数も、C\+\+ プログラムを終了します。  **exit** と **abort** の違いは、**exit** では C\+\+ ランタイムの終了プロセスが実行されますが \(グローバル オブジェクトのデストラクターが呼び出されます\)、**abort** ではプログラムが直ちに終了される点です。  詳細については、『ランタイム ライブラリ リファレンス』の「[abort](../c-runtime-library/reference/abort.md)」を参照してください。  
  
## 参照  
 [プログラムの終了](../Topic/Program%20Termination.md)