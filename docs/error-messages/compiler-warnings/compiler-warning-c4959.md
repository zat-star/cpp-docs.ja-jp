---
title: "コンパイラの警告 C4959 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4959"
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラの警告 C4959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アンマネージ構造体 'type' は、そのメンバーへのアクセスによって検証不可能なコードが生成されるため、\/clr:safe で定義できません  
  
 アンマネージ型のメンバーにアクセスすると、検証不可能な \(peverify.exe\) イメージが生成されます。  
  
 詳細については、「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
 この警告は、エラーとして表示されます。無効にするには、[warning](../../preprocessor/warning.md) プラグマ、または [\/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。  
  
 次の例では C4959 が生成されます。  
  
```  
// C4959.cpp // compile with: /clr:safe // Uncomment the following line to resolve. // #pragma warning( disable : 4959 ) struct X { int data; }; int main() { X x; x.data = 10;   // C4959 }  
```