---
title: "コンパイラ エラー C3383 | Microsoft Docs"
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
  - "C3383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3383"
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator new' は \/clr:safe でサポートされていません  
  
 **\/clr:safe** コンパイルの出力ファイルが検証可能なタイプ セーフのファイルであり、ポインターがサポートされていません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Visual C\+\+ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## 使用例  
 次の例では C3383 が生成されます。  
  
```  
// C3383.cpp // compile with: /clr:safe int main() { char* pCharArray = new char[256];  // C3383 }  
```