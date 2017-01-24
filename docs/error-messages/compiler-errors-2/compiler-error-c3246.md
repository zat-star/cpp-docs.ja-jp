---
title: "コンパイラ エラー C3246 | Microsoft Docs"
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
  - "C3246"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3246"
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3246
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 'type' から継承できません。'sealed' として宣言されている理由によります。  
  
 [sealed](../../misc/sealed.md) としてマークされているクラスは、他のクラスの基底クラスになることはできません。  
  
 次の例では C3246 が生成されます。  
  
```  
// C3246_2.cpp // compile with: /clr /LD ref class X sealed {}; ref class Y : public X {}; // C3246  
```  
  
 次の例では C3246 が生成されます。  
  
```  
// C3246.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> __sealed __gc class X {}; __gc class Y : public X {}; // C3246  
```