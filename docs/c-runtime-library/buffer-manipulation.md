---
title: "バッファー操作 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5c9c6b61c03671da0bfe3b58456291ad642aa7ff
ms.lasthandoff: 03/29/2017

---
# <a name="buffer-manipulation"></a>バッファー操作
次のルーチンを使用して、バイト単位でメモリの領域を操作します。  
  
### <a name="buffer-manipulation-routines"></a>バッファー操作ルーチン  
  
|ルーチン|用途|  
|-------------|---------|  
|[_memccpy](../c-runtime-library/reference/memccpy.md)|指定した文字または指定した数の文字がコピーされるまで、1 つのバッファーから別のバッファーに文字をコピーします|  
|[memchr、wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|バッファーで指定された文字が、指定した数の文字内で最初に発生した場所にポインターを返します|  
|[memcmp、wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|2 つのバッファーから指定した数の文字を比較します|  
|[memcpy、wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)、[memcpy_s、wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|1 つのバッファーから別のバッファーに指定した数の文字をコピーします|  
|[_memicmp、_memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|大文字小文字に関係なく、2 つのバッファーの指定された数の文字を比較します|  
|[memmove、wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)、[memmove_s、wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|1 つのバッファーから別のバッファーに指定した数の文字をコピーします|  
|[memset、wmemset](../c-runtime-library/reference/memset-wmemset.md)|指定された文字を使用して、バッファー内の指定したバイト数を初期化します|  
|[_swab](../c-runtime-library/reference/swab.md)|データのバイト数をスワップし、指定した場所にそのデータを格納します|  
  
 ソースとターゲットの領域が重なっている場合、`memmove` のみが完全なソースを正しくコピーすることを保証します。  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
