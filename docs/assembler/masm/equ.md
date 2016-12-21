---
title: "EQU | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EQU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EQU directive"
ms.assetid: 96db466a-1eab-45bd-a3c2-5a59bd754eab
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EQU
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最初のディレクティブは *式*  の数値を割り当てます。  
  
## 構文  
  
```  
  
      name EQU expression  
name EQU <text>  
```  
  
## 解説  
 *名前は*  後で再定義できません。  
  
 2 番目のディレクティブは指定したテキストを割り当てます。  その  *名前*  が別の  *テキストを*  後から指定できます。  [TEXTEQU](../../assembler/masm/textequ.md) を参照してください。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)