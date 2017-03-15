---
title: "/LOADCONFIG | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/loadconfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LOADCONFIG dumpbin オプション"
  - "LOADCONFIG dumpbin オプション"
  - "-LOADCONFIG dumpbin オプション"
ms.assetid: 24667afe-9bee-4f6e-ae72-f534c0050428
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LOADCONFIG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LOADCONFIG  
```  
  
## 解説  
 このオプションは、IMAGE\_LOAD\_CONFIG\_DIRECTORY 構造体をダンプします。これは Windows NT のローダーが使用するオプションの構造体で、WINNT.H において定義されています。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)