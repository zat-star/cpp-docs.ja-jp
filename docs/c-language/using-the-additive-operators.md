---
title: "加法演算子の使用 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94e2a63412e4fecd5f358659cc4bf02f90df57ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-additive-operators"></a>加法演算子の使用
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
  
 `i` の値は **float** の長さで乗算され、`&x[4]` に加算されます。 結果のポインター値は `x[8]` のアドレスです。  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 この例では、`x` の 3 番目の要素のアドレス (`x[i-2]` で指定) は、`x` の 5 番目の要素のアドレス (`x[i]` で指定) から減算されます。 違いを **float** の長さで割ります。結果は、整数値 2 です。  
  
## <a name="see-also"></a>参照  
 [C 加法演算子](../c-language/c-additive-operators.md)