---
title: "コンパイラ エラー C3213 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3213"
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

基底クラス 'base\_type' のアクセス可能性が 'derived\_type' よりも小さい  
  
 アセンブリから参照できる型は、公開されている基底クラスを使用する必要があります。  
  
 次の例では C3213 が生成されます。  
  
```  
// C3213.cpp // compile with: /clr private ref struct privateG { public: int i; }; public ref struct publicG { public: int i; }; public ref struct V : public privateG {   // C3213 public: int j; }; public ref struct W: public publicG {   // OK public: int j; };  
```