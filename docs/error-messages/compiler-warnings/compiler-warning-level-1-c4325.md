---
title: "コンパイラの警告 (レベル 1) C4325 | Microsoft Docs"
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
  - "C4325"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4325"
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4325
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**無視された標準セクション '**   
 ***section* ' の属性**  
  
 標準セクションの属性は変更できません。  たとえば、次のようになります。  
  
```  
#pragma section(".sdata", long)  
```  
  
 この場合、**short** データ型を使用する `.sdata` 標準セクションは **long** データ型で上書きされます。  
  
 属性を変更できない標準セクションは、次のとおりです。  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 後でさらにセクションが追加される場合があります。  
  
## 参照  
 [セクション](../../preprocessor/section.md)