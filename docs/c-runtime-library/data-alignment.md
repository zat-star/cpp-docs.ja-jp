---
title: "データの整列 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data.alignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データのアラインメント [C++]"
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# データの整列
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の C ランタイム関数はデータ配置をサポートします。  
  
### データの整列ルーチン  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[\_aligned\_free](../c-runtime-library/reference/aligned-free.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)で割り当てられたメモリ ブロックを解放します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_free\_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(デバッグのみ\) で割り当てられたメモリ ブロックを解放します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)|指定された配置境界にメモリを割り当てます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_malloc\_dbg](../Topic/_aligned_malloc_dbg.md)|デバッグのヘッダーと上書きバッファーします \(デバッグ バージョンだけ\) 用の領域で指定された配置境界にメモリを割り当てます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_msize](../c-runtime-library/reference/aligned-msize.md)|ヒープに割り当てられたメモリ ブロックのサイズを返します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_msize\_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|ヒープで割り当てられたメモリ ブロックのサイズを返します \(デバッグ バージョンのみ\)。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|指定された配置境界にメモリを割り当てます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_malloc\_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|指定された配置境界にメモリを割り当てます \(デバッグ バージョンのみ\)。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)で割り当てられたメモリ ブロックのサイズを変更します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_realloc\_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) します \(デバッグ バージョンだけ\) で割り当てられたメモリ ブロックのサイズを変更します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリに変更し、0 を初期化しますメモリ ブロックのサイズを返します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_offset\_recalloc\_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリに変更し、0 を初期化しますメモリ ブロックのサイズ \(デバッグ バージョンだけ\)。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_realloc](../c-runtime-library/reference/aligned-realloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)で割り当てられたメモリ ブロックのサイズを変更します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_realloc\_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) します \(デバッグ バージョンだけ\) で割り当てられたメモリ ブロックのサイズを変更します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリに変更し、0 を初期化しますメモリ ブロックのサイズを返します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_aligned\_recalloc\_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリに変更し、0 を初期化しますメモリ ブロックのサイズ \(デバッグ バージョンだけ\)。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)