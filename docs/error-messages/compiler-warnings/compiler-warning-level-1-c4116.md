---
title: "コンパイラの警告 (レベル 1) C4116 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4116"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4116"
ms.assetid: 25434ef3-061e-4252-91a5-0fe2a4b2ffb3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4116
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無名の型が式のカッコの中で定義されました。  
  
 名前のない構造体、共用体、または列挙型が、式のかっこの中で定義されています。  定義は無意味なものとなります。  
  
 C の関数呼び出しでは、定義はグローバル スコープとなります。  C\+\+ の関数呼び出しでは、定義は呼び出される関数と同じスコープとなります。