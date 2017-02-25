---
title: "/IMPORTS (DUMPBIN) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/imports"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPORTS dumpbin オプション"
  - "IMPORTS dumpbin オプション"
  - "-IMPORTS dumpbin オプション"
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /IMPORTS (DUMPBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPORTS[:file]  
```  
  
 このオプションは、実行可能ファイルまたは DLL にインポートされる DLL の一覧 \(静的にリンクされる DLL と[遅延読み込みされる DLL](../../build/reference/linker-support-for-delay-loaded-dlls.md) の両方\)、およびこれらの各 DLL から個別にインポートされるすべての情報を表示します。  
  
 省略可能な `file` パラメーターを指定すると、その DLL だけに対するインポートを表示できます。  たとえば、次のようになります。  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## 解説  
 このオプションによって出力される内容は、[\/EXPORTS](../../build/reference/dash-exports.md) で出力される内容と似ています。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)