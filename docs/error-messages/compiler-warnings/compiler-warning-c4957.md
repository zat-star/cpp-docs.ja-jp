---
title: "コンパイラの警告 C4957 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4957"
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# コンパイラの警告 C4957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast': 'cast\_from' から 'cast\_to' への明示的なキャストは検証できません  
  
 キャストにより、検証不可能なイメージが生成されます。  
  
 安全なキャストもあります \(ユーザー定義の変換をトリガーする `static_cast`、`const_cast` など\)。[safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) は、検証可能なコードを生成することが保証されています。  
  
 詳細については、「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
 この警告は、エラーとして表示されます。無効にするには、[warning](../../preprocessor/warning.md) プラグマ、または [\/wd](../../build/reference/compiler-option-warning-level.md) コンパイラ オプションを使用します。  
  
 次の例では C4957 が生成されます。  
  
```  
// C4957.cpp // compile with: /clr:safe // #pragma warning( disable : 4957 ) using namespace System; int main() { Object ^ o = "Hello, World!"; String ^ s = static_cast<String^>(o);   // C4957 String ^ s2 = safe_cast<String^>(o);   // OK }  
```