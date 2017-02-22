---
title: "_query_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_mode"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "query_new_mode"
  - "_query_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_mode 関数"
  - "ハンドラー モード"
  - "query_new_mode 関数"
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc`の `_set_new_mode` によって設定された new ハンドラー モードを示す整数を返します。  
  
## 構文  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## 戻り値  
 現在の new ハンドラー モード、`malloc`の \(0 または 1 を返します。  戻り値 1 は、メモリの割り当てに失敗 `malloc` が new ハンドラー ルーチンを呼び出しています; 戻り値 0 はことを示します。  
  
## 解説  
 [malloc](../../c-runtime-library/reference/malloc.md)の C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 関数によって設定された new ハンドラー モードを示す整数 `_query_new_mode` C\+\+ 関数の戻り値。  new ハンドラー モードは、メモリの割り当てに失敗 `malloc` ように [\_set\_new\_handler](../Topic/_set_new_handler.md)で設定された new ハンドラー ルーチンを呼び出すかどうかを示します。  既定で、`malloc` は失敗の new ハンドラー ルーチンを呼び出しません。  メモリを割り当てると **new** の演算子は、ように失敗した `malloc` の呼び出しで new ハンドラー ルーチン同様にこの動作をオーバーライドするには `_set_new_mode` を使用できます。  詳細については、" *C\+\+ Language Reference*" [演算子の削除](../Topic/operator%20delete%20Function.md) と [新しい演算子](../../misc/operator-new-function.md) 関数を参照します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_query_new_mode`|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)