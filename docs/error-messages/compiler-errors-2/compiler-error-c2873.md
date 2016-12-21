---
title: "コンパイラ エラー C2873 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2873"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2873"
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2873
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : シンボルを using 宣言の中で使用することはできません。  
  
 `using` ディレクティブに [namespace](../Topic/namespace%20Declaration.md) キーワードが指定されていません。  この場合、コンパイラはコードを [using ディレクティブ](../../misc/using-directive-cpp.md)ではなく [using 宣言](../../cpp/using-declaration.md)として解釈します。