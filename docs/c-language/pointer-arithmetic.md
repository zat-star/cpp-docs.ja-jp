---
title: "ポインターの算術演算 | Microsoft Docs"
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
  - "算術演算ポインター"
  - "ポインターの算術演算"
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ポインターの算術演算
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ポインターと整数を含む加法演算子は、ポインターのオペランドが配列のメンバーを扱い、整数値が同じ配列の境界内のオフセットを生成する場合にのみ意味のある結果が得られます。  整数値がアドレス オフセットに変換されるとき、コンパイラは同じサイズのメモリ位置が元のアドレスとオフセットの間にあるものと仮定します。  
  
 この想定は配列のメンバーに対して有効です。  定義上、配列は同じ型の一連の値です。その要素は連続するメモリ位置に配置されます。  ただし、配列要素を除くすべての型のストレージに、識別子の同じ型が格納されることは保証されません。  つまり、空白はメモリ位置 \(同じ種類の偶数位置\) 間に表示される可能性があります。  したがって、値ではなく配列要素のアドレスに対する加算と減算の結果は未定義です。  
  
 同様に、2 つのポインター値を減算する場合、変換では、オペランドで指定されたアドレス間には空白のない同じの型の値だけが指定されているものと見なされます。  
  
## 参照  
 [C 加法演算子](../c-language/c-additive-operators.md)