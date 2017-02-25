---
title: "コンパイラの警告 C4936 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4936"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4936"
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラの警告 C4936
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この \_\_declspec は、\/clr または \/clr:pure でコンパイルされるときのみサポートされます  
  
 `__declspec` 修飾子が使用されましたが、この `__declspec` 修飾子は、いずれかの [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) オプションでコンパイルされた場合にのみ有効です。  
  
 詳細については、「[appdomain](../Topic/appdomain.md)」および「[process](../../cpp/process.md)」を参照してください。  
  
 C4936 は、常にエラーとして表示されます。[warning](../../preprocessor/warning.md) プラグマを使用して、C4936 を無効にすることができます。  
  
 次の例では C4936 が生成されます。  
  
```  
// C4936.cpp // compile with: /c // #pragma warning (disable : 4936) __declspec(process) int i;   // C4936 __declspec(appdomain) int j;   // C4936  
```