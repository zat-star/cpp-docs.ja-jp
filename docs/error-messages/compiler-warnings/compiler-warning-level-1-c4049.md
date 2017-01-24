---
title: "コンパイラの警告 (レベル 1) C4049 | Microsoft Docs"
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
  - "C4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4049"
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : 行番号の出力を中止します。  
  
 このファイルのソース行は、16,777,215 \(2<sup>24</sup>\-1\) 行を超えています。  コンパイラは 16,777,215 行目で番号指定を停止します。  
  
 16,777,215 行目より後のコードについては、以下の問題が発生します。  
  
-   イメージには、行番号のデバッグ情報が含まれません。  
  
-   報告される診断で、行番号が正しくない場合があります。  
  
-   .asm リスティング \(\/FAs\) の行番号が正しくない場合があります。