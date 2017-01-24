---
title: "alloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\_alloca](../c-runtime-library/reference/alloca.md) は、16 バイトでアライメントされている必要があります。また、フレーム ポインターを使用する必要があります。  
  
 割り当てられたスタックは、以降の呼び出し先関数のパラメーターに対して、その下の領域を割り当てる必要があります。詳細については、「[スタック割り当て](../build/stack-allocation.md)」を参照してください。  
  
## 参照  
 [スタックの使用](../build/stack-usage.md)