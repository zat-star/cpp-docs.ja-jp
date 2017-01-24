---
title: "コンパイラ エラー C3205 | Microsoft Docs"
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
  - "C3205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3205"
ms.assetid: 802d306e-5ff3-4491-8a22-c5f1c072d005
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

テンプレート パラメーター 'template' の引数リストがありません  
  
 [template](../Topic/Template%20Specifications.md) パラメーターがありません。  
  
 次の例では C3205 が生成されます。  
  
```  
// C3205.cpp template<template<class> class T> struct A { typedef T unparameterized_type;   // C3205 // try the following line instead // typedef T<int> unparameterized_type; }; template <class T> struct B { typedef int value_type; }; int main() { A<B> x; }  
```