---
title: "Range of Integer Values (整数値の範囲) | Microsoft Docs"
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
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 5770c8efda6b044f99621d4a280e415fa825648f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="range-of-integer-values"></a>Range of Integer Values (整数値の範囲)
**ANSI 3.1.2.5** 整数のさまざまな型の表現と値セット  
  
 整数は 32 ビット (4 バイト) を含みます。 符号付き整数は、2 の補数形式で表されます。 最上位ビットは符号を表し、負の数ならば 1、正の数とゼロならば 0 です。 値は次のとおりです。  
  
|型|最小および最大|  
|----------|-------------------------|  
|**unsigned short**|0 から 65535|  
|`signed short`|-32768 から 32767|  
|`unsigned long`|0 から 4294967295|  
|**signed long**|-2147483648 から 2147483647|  
  
## <a name="see-also"></a>関連項目  
 [整数](../c-language/integers.md)
