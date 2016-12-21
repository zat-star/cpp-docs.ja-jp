---
title: "コンパイラの警告 (レベル 4) C4668 | Microsoft Docs"
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
  - "C4668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4668"
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' は、'directives' を '0' に置換するプリプロセッサ マクロとして定義されていません。  
  
 プリプロセッサ ディレクティブで、定義されていないシンボルが使用されています。  このシンボルは false として評価されます。  シンボルを定義するには、[\#define ディレクティブ](../../preprocessor/hash-define-directive-c-cpp.md)または [\/D](../../build/reference/d-preprocessor-definitions.md) コンパイラ オプションを使用できます。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
## 使用例  
 次の例では警告 C4668 が生成されます。  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```