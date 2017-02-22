---
title: "式の配列 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 式"
  - "式 [C++], 配列"
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 式の配列
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

配列型の ID が `sizeof`、address\-of \(**&**\)、または参照の初期化以外の式に出現すると、最初の配列要素へのポインターに変換されます。  次に例を示します。  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 ポインター `psz` は、配列 `szError1` の最初の要素をポイントします。  配列は、ポインターとは異なり、変更できる左辺値ではないことに注意してください。  したがって、次の割り当ては正しくありません。  
  
```  
szError1 = psz;  
```  
  
## 参照  
 [配列](../Topic/Arrays%20\(C++\).md)