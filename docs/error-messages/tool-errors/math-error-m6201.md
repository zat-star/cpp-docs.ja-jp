---
title: "数値演算エラー M6201 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17de7fab7b41a5a8acc2fed2f3c8185f66aadd9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6201"></a>数値演算エラー M6201
'function': _DOMAIN エラー  
  
 指定された関数の引数は、その関数の有効な入力値のドメイン外でした。  
  
## <a name="example"></a>例  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 このエラーが、`_matherr`関数名、その引数、およびエラーの種類を持つ関数です。 書き直すことができます、`_matherr`特定の浮動小数点演算の実行時エラーの処理をカスタマイズする関数。