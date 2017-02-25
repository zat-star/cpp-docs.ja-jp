---
title: "コンパイラの警告 C4972 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4972"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4972"
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラの警告 C4972
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アンボックス操作の結果を左辺の値として扱う、または直接変更することは検証可能ではありません  
  
 ハンドルの値型への逆参照 \(ボックス化解除\) およびその後の割り当てを検証できません。  
  
 詳細については、「[Boxing](../../windows/boxing-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4972 警告が生成されます。  
  
```  
// C4972.cpp // compile with: /clr:safe using namespace System; ref struct R { int ^ p;   // a value type }; int main() { R ^ r = gcnew R; *(r->p) = 10;   // C4972 // OK r->p = 10; Console::WriteLine( r->p ); Console::WriteLine( *(r->p) ); }  
```