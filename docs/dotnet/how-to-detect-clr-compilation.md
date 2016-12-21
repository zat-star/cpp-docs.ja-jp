---
title: "方法: Detect /clr コンパイルを検出する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr コンパイラ オプション [C++], 検出 (使用を)"
  - "コンパイル, 検出 (/clr を)"
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Detect /clr コンパイルを検出する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr**  を指定してモジュールをコンパイルしているかどうかを調べるには、`_MANAGED` マクロ、または `_M_CEE` マクロを使用します。  詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 マクロの詳細については、「[定義済みマクロ](../preprocessor/predefined-macros.md)」を参照してください。  
  
## 使用例  
  
```  
// detect_CLR_compilation.cpp  
// compile with: /clr  
#include <stdio.h>  
  
int main() {  
   #if (_MANAGED == 1) || (_M_CEE == 1)  
      printf_s("compiling with /clr\n");  
   #else  
      printf_s("compiling without /clr\n");  
   #endif  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)