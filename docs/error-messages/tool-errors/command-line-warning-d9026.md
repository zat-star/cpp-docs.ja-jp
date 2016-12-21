---
title: "コマンド ラインの警告 D9026 | Microsoft Docs"
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
  - "D9026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9026"
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コマンド ラインの警告 D9026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オプションはコマンド ライン全体に適用されます。  
  
 コマンド ラインで、ファイル名の指定の後ろにオプションが指定されています。  このオプションは、その前に指定されているファイルに適用されます。  
  
 たとえば、コマンド ラインに次のように指定します。  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 この場合、VERDI.c というファイルは、既定の \/G4 オプションではなく、\/G5 オプションを使用してコンパイルされます。  
  
 古いバージョンでは、この仕様とは異なり、ファイル名の前に指定されたオプションしかファイルに適用されません。そのようなコンパイラでは、ファイル VERDI.c は \/G4 オプションでコンパイルされ、ファイル PUCCINI.c は \/G5 オプションでコンパイルされます。