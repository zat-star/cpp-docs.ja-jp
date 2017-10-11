---
title: "Signed Bitwise Operations (符号付きビット処理演算) | Microsoft Docs"
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
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 9ffc5335bb28e619f166a524083937d17a59bb97
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="signed-bitwise-operations"></a>Signed Bitwise Operations (符号付きビット処理演算)
**ANSI 3.3** 符号付き整数のビットごとの演算の結果  
  
 符号付き整数のビットごとの演算は、符号なし整数のビットごとの演算と同じように動作します。 たとえば、`-16 & 99` は、バイナリでは次のように表されます。  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 ビットごとの AND の結果は 96 です。  
  
## <a name="see-also"></a>関連項目  
 [整数](../c-language/integers.md)
