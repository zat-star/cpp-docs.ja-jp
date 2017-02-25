---
title: "コンパイラの警告 (レベル 1) C4964 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4964"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4964"
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4964
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最適化のオプションが指定されませんでした。プロファイル情報は収集されません  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) および [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) が指定されましたが、最適化が要求されませんでした。したがって、.pgc ファイルは生成されず、ガイド付き最適化のプロファイルも実行できません。  
  
 アプリケーションを実行するときに .pgc ファイルを生成する場合は、いずれかの [\/O](../../build/reference/o-options-optimize-code.md) コンパイラ オプションを指定します。  
  
 次の例では警告 C4964 が生成されます。  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```