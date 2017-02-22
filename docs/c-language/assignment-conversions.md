---
title: "代入変換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "代入の変換"
  - "変換, 割り当て"
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 代入変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

代入演算では、代入値の型が、代入を受け取る変数の型に変換されます。  C では、変換によって情報が失われる場合でも、整数型と浮動小数点型の間で代入による変換を実行できます。  使用される変換メソッドは、「[Usual Arithmetic Conversions \(通常の算術変換\)](../c-language/usual-arithmetic-conversions.md)」および以下の各セクションで説明されているように、代入に関与する型によって決まります。  
  
-   [Conversions from Signed Integral Types \(符号付き整数型からの変換\)](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Conversions from Unsigned Integral Types \(符号なし整数型からの変換\)](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Conversions from Floating\-Point Types \(浮動小数点型からの変換\)](../Topic/Conversions%20from%20Floating-Point%20Types.md)  
  
-   [Conversions to and from Pointer Types \(ポインター型との間の変換\)](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Conversions from Other Types \(他の型からの変換\)](../c-language/conversions-from-other-types.md)  
  
 型修飾子は変換の許容性には影響しませんが、代入の左辺で **const** 値は使用できません。  
  
## 参照  
 [型変換](../c-language/type-conversions-c.md)