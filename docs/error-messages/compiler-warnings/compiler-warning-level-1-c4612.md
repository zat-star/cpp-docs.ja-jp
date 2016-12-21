---
title: "コンパイラの警告 (レベル 1) C4612 | Microsoft Docs"
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
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクルード ファイル名にエラーがあります  
  
 この警告は、ファイル名が正しくないか、不足している場合に、**\#pragma include\_alias** で発生します。  
  
 **\#pragma include\_alias** ステートメントへの引数は、引用形式 \(**"***filename***"**\) または山かっこ形式 \(**\<***filename***\>**\) を使用できますが、両方とも同じ形式を使用する必要があります。  
  
## 使用例  
  
```  
// C4612.cpp // compile with: /W1 /LD #pragma include_alias("StandardIO", <stdio.h>) // C4612  
```