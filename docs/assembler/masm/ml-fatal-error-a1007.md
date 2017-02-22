---
title: "ML Fatal Error A1007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1007"
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**入れ子のレベルが深すぎます**  
  
 アセンブラーは入れ子の限界に到達しました。  制限は注意する別の方法ではレベル 20 以外。  
  
 は次のいずれかのレベルが深すぎます :  
  
-   [.IF](../Topic/.IF.md) [.REPEAT](../../assembler/masm/dot-repeat.md)または [.WHILE](../../assembler/masm/dot-while.md) 高レベルのディレクティブ。  
  
-   構造体の定義。  
  
-   条件付きアセンブリのディレクティブ。  
  
-   プロシージャ定義。  
  
-   [PUSHCONTEXT](../../assembler/masm/pushcontext.md) のディレクティブ \(制約は 10 になります。  
  
-   部分定義。  
  
-   インクルード ファイル。  
  
-   マクロ。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)