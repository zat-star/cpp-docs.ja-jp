---
title: "コンパイラの警告 C4956 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4956"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4956"
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4956
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : この型は検証可能ではありません  
  
 この警告は、[\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) が指定され、コードに検証不可能な型が含まれている場合に生成されます。  
  
 詳細については、「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
 この警告は、エラーとして表示されます。無効にするには、[warning](../../preprocessor/warning.md) プラグマ、または [\/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。  
  
 次の例では C4956 が生成されます。  
  
```  
// C4956.cpp // compile with: /clr:safe int* p;   // C4956  
```