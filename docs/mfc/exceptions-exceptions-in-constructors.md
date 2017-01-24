---
title: "例外処理 : コンストラクターの例外処理 | Microsoft Docs"
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
  - "コンストラクター [C++], 例外"
  - "例外, コンストラクターで"
  - "スロー (例外を), コンストラクターで"
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : コンストラクターの例外処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[例外: 独自の関数が例外をスローする](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)"で説明されているように、オブジェクト、およびメモリ割り当てが例外をスローする前に行ったコンストラクターが例外をスローした場合、クリーンアップしてください。  
  
 コンストラクターで例外をスローすると、コンストラクターが呼び出されるまで、オブジェクトのメモリ自体が既に割り当てられています。  したがって、コンパイラは自動的に例外がスローされた後にオブジェクトによって占められていたメモリを解放します。  
  
 詳細については、「[例外: 例外オブジェクトの解放](../Topic/Exceptions:%20Freeing%20Objects%20in%20Exceptions.md)」を参照してください。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)