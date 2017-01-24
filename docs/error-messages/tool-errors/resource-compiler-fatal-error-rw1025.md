---
title: "リソース コンパイラの致命的なエラー RW1025 | Microsoft Docs"
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
  - "RW1025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1025"
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの致命的なエラー RW1025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Out of far heap memory  
  
 大量のメモリを使用している可能性がある、メモリ常駐ソフトウェアがないかどうかを確認してください。  CHKDSK プログラムを使用すると、現在のメモリ量を確認できます。  
  
 大きなリソース ファイルを生成する場合は、リソース スクリプト ファイルを 2 つに分割してください。  2 つの .res ファイルを生成した後で、次に示す MS\-DOS コマンド ラインを使用して結合してください。  
  
```  
copy first.res /b + second.res /b full.res  
```