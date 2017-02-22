---
title: "加法演算子の使用 | Microsoft Docs"
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
  - "加法演算子"
  - "演算子 [C++], 加算"
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 加法演算子の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

加算演算子と減算演算子を示す次の例は、これらの宣言を使用します。  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 これらのステートメントは等価です。  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 `i` の値は **float** の長さで乗算され、`&x[4]` に加算されます。  結果のポインター値は `x[8]` のアドレスです。  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 この例では、`x` の 3 番目の要素のアドレス \(`x[i–2]` で指定\) は、`x` の 5 番目の要素のアドレス \(`x[i]` で指定\) から減算されます。  違いを **float** の長さで割ります。結果は、整数値 2 です。  
  
## 参照  
 [C 加法演算子](../c-language/c-additive-operators.md)