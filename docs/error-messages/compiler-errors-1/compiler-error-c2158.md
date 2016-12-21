---
title: "コンパイラ エラー C2158 | Microsoft Docs"
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
  - "C2158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2158"
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': \#pragma make\_public ディレクティブは、現在テンプレートでないネイティブの型にのみサポートされています  
  
 [make\_public](../../preprocessor/make-public.md) プラグマは、ネイティブの非テンプレート型にのみ適用できます。  
  
## 使用例  
 次の例では C2158 が生成されます。  
  
```  
// C2158.cpp // compile with: /clr /c ref class A {}; #pragma make_public(A)   // C2158 template< typename T > class B {}; #pragma make_public(B)   // C2158 #pragma make_public(B<int>)   // C2158 void C () {} #pragma make_public(C)   // C2158 class D {}; #pragma make_public(D)   // OK  
```