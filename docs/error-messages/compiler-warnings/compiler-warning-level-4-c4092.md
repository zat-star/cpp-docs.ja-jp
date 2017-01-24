---
title: "コンパイラの警告 (レベル 4) C4092 | Microsoft Docs"
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
  - "C4092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4092"
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

sizeof 演算子が 'unsigned long' の値を返しました。  
  
 `sizeof` 演算子のオペランドが大きすぎたため、`sizeof` が unsigned **long** を返しました。  この警告は、Microsoft 拡張機能 \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md) オプションで指定\) を指定した場合に発生します。  ANSI 互換のオプション \(\/Za\) を使用している場合は、結果が切り捨てられます。