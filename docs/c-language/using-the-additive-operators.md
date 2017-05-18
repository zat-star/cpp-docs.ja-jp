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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 04e23f9694193a05d48b7fcdff717d06e448e877
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

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
  
## <a name="see-also"></a>関連項目  
 [C 加法演算子](../c-language/c-additive-operators.md)
