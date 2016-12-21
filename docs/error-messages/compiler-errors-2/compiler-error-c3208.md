---
title: "コンパイラ エラー C3208 | Microsoft Docs"
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
  - "C3208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3208"
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': クラス テンプレート 'class' のテンプレート パラメーター リストは、テンプレート template パラメーター 'parameter' のテンプレート パラメーター リストと一致しません  
  
 テンプレート template パラメーターには、指定されたクラス テンプレートと同じ数のテンプレート パラメーターがありません。  
  
 次の例では C3208 が生成されます。  
  
```  
// C3208.cpp template <template <class T> class TT > int f(); template <class T1, class T2> struct S; template <class T1> struct R; int i = f<S>();   // C3208 // try the following line instead // int i = f<R>();  
```