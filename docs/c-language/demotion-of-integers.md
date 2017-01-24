---
title: "整数の下位変換 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "整数の降格"
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 整数の下位変換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.2.1.2** 値を表すことができない場合に、整数を短い符号付き整数に変換したか、符号なし整数を同じ長さの符号付き整数に変換したときの結果  
  
 **long** 整数が **short** にキャストされるか、**short** が `char` にキャストされるときには、下位バイトが保持されます。  
  
 たとえば、次のコード行、  
  
```  
short x = (short)0x12345678L;  
```  
  
 では、値 0x5678 が `x` に代入されます。また、次のコード行、  
  
```  
char y = (char)0x1234;  
```  
  
 では、値 0x34 が `y` に代入されます。  
  
 符号付き変数が符号なしに変換されるときと、その逆で、ビット パターンは変わりません。  たとえば、–2 \(0xFE\) を符号なしの値にキャストすると、254 \(これも 0xFE\) になります。  
  
## 参照  
 [整数](../Topic/Integers.md)