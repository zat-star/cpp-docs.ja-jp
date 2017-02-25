---
title: "メイクファイルでの長いファイル名 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "長いファイル名"
  - "NMAKE プログラム, 長いファイル名"
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# メイクファイルでの長いファイル名
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

長いファイル名は、次のように二重引用符で囲みます。  
  
```  
all : "VeryLongFileName.exe"  
```  
  
## 参照  
 [メイクファイルの内容](../build/contents-of-a-makefile.md)