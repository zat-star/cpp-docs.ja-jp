---
title: "メモリ割り当て | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メモリの割り当て, ルーチン"
  - "メモリ, 割り当て"
  - "メモリ, 管理"
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# メモリ割り当て
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのルーチンを使用して、メモリを割り当て、解放、および再割り当てします。  
  
### メモリ割り当てルーチン  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|----------|--------|---------------------------|  
|[\_alloca](../c-runtime-library/reference/alloca.md), [\_malloca](../c-runtime-library/reference/malloca.md)|スタックからメモリを割り当てます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[calloc](../c-runtime-library/reference/calloc.md)|配列の記憶域を割り当て、割り当てられたブロック内のすべてのバイトを 0 に初期化します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_calloc\_dbg](../c-runtime-library/reference/calloc-dbg.md)|`calloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|割り当てられたブロックを解放します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|割り当てられたブロックを解放します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_expand](../Topic/_expand.md)|メモリ ブロックを移動しないで拡大および縮小します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_expand\_dbg](../Topic/_expand_dbg.md)|`_expand` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[free](../c-runtime-library/reference/free.md)|割り当てられたブロックを解放します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_free\_dbg](../c-runtime-library/reference/free-dbg.md)|`free` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_freea](../c-runtime-library/reference/freea.md)|スタックから割り当てられたブロックを解放します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_get\_heap\_handle](../c-runtime-library/reference/get-heap-handle.md)|CRT ヒープの Win32 HANDLE を取得します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_heapadd](../c-runtime-library/heapadd.md)|ヒープにメモリを追加します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_heapchk](../c-runtime-library/reference/heapchk.md)|ヒープの一貫性をチェックします。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_heapmin](../c-runtime-library/reference/heapmin.md)|ヒープ内の未使用のメモリを解放します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_heapset](../c-runtime-library/heapset.md)|空きヒープ エントリに、指定された値を設定します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_heapwalk](../Topic/_heapwalk.md)|ヒープ内の各エントリに関する情報を返します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[malloc](../c-runtime-library/reference/malloc.md)|ヒープからメモリ ブロックを割り当てます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)|`malloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_msize](../Topic/_msize.md)|割り当てられたブロックのサイズを返します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_msize\_dbg](../c-runtime-library/reference/msize-dbg.md)|`_msize` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[new](../c-runtime-library/operator-new-crt.md)|ヒープからメモリ ブロックを割り当てます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|ヒープからメモリ ブロックを割り当てます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_query\_new\_handler](../c-runtime-library/reference/query-new-handler.md)|`_set_new_handler` によって設定された現在の新しいハンドラー ルーチンのアドレスを返します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_query\_new\_mode](../c-runtime-library/reference/query-new-mode.md)|`malloc` に対して `_set_new_mode`  によって設定された新しいハンドラー モードを示す整数を返します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[realloc](../c-runtime-library/reference/realloc.md)|ブロックを新しいサイズに再割り当てします。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_realloc\_dbg](../c-runtime-library/reference/realloc-dbg.md)|`realloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_set\_new\_handler](../Topic/_set_new_handler.md)|`new` 演算子が \(メモリの割り当てに\) 失敗したときにエラー処理機構を有効にし、標準テンプレート ライブラリ \(STL\) のコンパイルを有効にします。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_set\_new\_mode](../c-runtime-library/reference/set-new-mode.md)|`malloc` の新しいハンドラー モードを設定します。|該当なし。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)