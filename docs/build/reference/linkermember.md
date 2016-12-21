---
title: "/LINKERMEMBER | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkermember"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINKERMEMBER dumpbin オプション"
  - "LINKERMEMBER dumpbin オプション"
  - "-LINKERMEMBER dumpbin オプション"
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LINKERMEMBER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINKERMEMBER[:{1|2}]  
```  
  
## 解説  
 このオプションは、ライブラリで定義されているパブリック シンボルを出力します。  引数に 1 を指定すると、シンボルがオブジェクト順にオフセット付きで出力されます。  引数に 2 を指定すると、オブジェクトのオフセットとインデックス番号が出力されます。その後、シンボルがアルファベット順にオブジェクト インデックス付きで出力されます。  この両方を出力するには、引数で値を指定せずに \/LINKERMEMBER だけを指定します。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)