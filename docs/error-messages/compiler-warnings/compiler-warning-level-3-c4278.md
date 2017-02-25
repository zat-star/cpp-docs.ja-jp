---
title: "コンパイラの警告 (レベル 3) C4278 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4278"
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 3) C4278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': タイプ ライブラリ 'tlb' の識別子は既にマクロです。'rename' 修飾子を使用してください。  
  
 [\#import](../Topic/%23import%20Directive%20\(C++\).md) を使用すると、インポートする typelib 内の識別子は、識別子 ***identifier*** の宣言を試みます。  ただし、これは既に有効なシンボルです。  
  
 `#import` **rename** 属性を使用して、タイプ ライブラリ内のシンボルにエイリアスを割り当ててください。