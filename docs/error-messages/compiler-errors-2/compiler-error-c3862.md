---
title: "コンパイラ エラー C3862 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3862"
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数': \/clr:pure または \/clr:safe を伴うアンマネージ関数をコンパイルできません  
  
 **\/clr:pure** または **\/clr:safe** を指定してコンパイルすると、MSIL のみのイメージが生成されます。これはネイティブ \(アンマネージ\) コードを持たないイメージです。したがって、**\/clr:pure** または **\/clr:safe**  を指定したコンパイルでは、`unmanaged` プラグマは使用できません。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」および「[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)」を参照してください。  
  
## 使用例  
 次の例では警告 C3862 が生成されます。  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```