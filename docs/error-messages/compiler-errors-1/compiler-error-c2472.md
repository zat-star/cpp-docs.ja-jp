---
title: "コンパイラ エラー C2472 | Microsoft Docs"
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
  - "C2472"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2472"
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2472
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' を 'message' マネージ コードで生成できません。混合イメージを生成するには、\/clr と共にコンパイルしてください  
  
 このエラーは、純粋な共通言語ランタイム \(CLR\) の環境内で、マネージ コードでサポートされていない型を使用すると発生します。 エラーを解決するには、**\/clr** を使用してコンパイルします。  
  
## 使用例  
 次の例では警告 C2472 が生成されます。  
  
```  
// C2472.cpp // compile with: /clr:pure // C2472 expected #include <cstdlib> int main() { int * __ptr32 p32; int * __ptr64 p64; p32 = (int * __ptr32)malloc(4); p64 = p32; }  
```  
  
## 参照  
 [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)