---
title: "コンパイラ エラー C3295 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3295"
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラ エラー C3295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#pragma pragma' は、グローバルまたは名前空間スコープでのみ使用できます  
  
 一部のプラグマは関数内では使用できません。  詳細については、「[プラグマ ディレクティブと \_\_Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。  
  
## 使用例  
 次の例では C3295 が生成されます。  
  
```  
// C3295.cpp int main() { #pragma managed   // C3295 }  
```