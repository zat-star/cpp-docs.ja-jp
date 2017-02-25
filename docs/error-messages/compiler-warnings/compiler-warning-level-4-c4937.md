---
title: "コンパイラの警告 (レベル 4) C4937 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4937"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4937"
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4937
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'text1' と 'text2' を、'directive' への引数として区別できません  
  
 コンパイラがディレクティブへの引数を処理するしくみにより、複数のテキスト表現 \(単一および二重のアンダースコア形式\) を持つキーワードなど、コンパイラにとって意味を持つ名前は区別することができません。  
  
 このような文字列の例には、\_\_cdecl および \_\_forceinline があります。  \/Za の下では、二重アンダースコア形式のみが有効であることに注意してください。  
  
 次の例では C4937 が生成されます。  
  
```  
// C4937.cpp // compile with: /openmp /W4 #include "omp.h" int main() { #pragma omp critical ( __leave )   // C4937 ; // OK #pragma omp critical ( leave ) ; }  
```