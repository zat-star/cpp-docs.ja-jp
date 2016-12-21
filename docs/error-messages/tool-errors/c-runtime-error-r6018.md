---
title: "C ランタイム エラー R6018 | Microsoft Docs"
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
  - "R6018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6018"
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unexpected heap error  
  
 プログラムがメモリ管理操作を行っているときに、予期せぬエラーが発生しました。  
  
 通常、このエラーは、プロセスがランタイム ヒープ データを不正に変更しようとしたときに発生します。  ランタイム コードやオペレーティング システム コードの内部エラーが発生している可能性もあります。  
  
 `_heapchk` 関数や `_heapwalk` 関数を含むライブラリを使用できる場合は、これらの関数を使ってエラーを診断できます。