---
title: "_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc"
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
  - "_recalloc"
  - "recalloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_recalloc 関数"
  - "recalloc 関数"
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`realloc` と `calloc` の組み合わせです。  メモリの配列を再割り当てし、0 に要素を初期化します。  
  
## 構文  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### パラメーター  
 `memblock`  
 前に割り当てられたメモリ ブロックへのポインター。  
  
 `num`  
 要素の数。  
  
 `size`  
 各要素のバイト数。  
  
## 戻り値  
 `_recalloc` が 再割り当てされる場合 \(移動\) メモリ ブロックの `void` のポインターを返します。  
  
 特定のサイズにブロックを展開する十分な使用可能なメモリがある元のブロックは変更されず、`NULL` が返されます。  
  
 要求されたサイズがゼロの場合、`memblock` が指す;ブロックが解放されます。戻り値は `NULL`であり、`memblock` は解放されたブロックの指を保持されます。  
  
 戻り値は適切にどの型のオブジェクトを格納するために配置されることが保証されるストレージ領域を指します。  `void`以外の型へのポインターを取得するには、戻り値の型キャストを使用してください。  
  
## 解説  
 \_`recalloc` の関数の変更に割り当てられたメモリ ブロックのサイズ。  `memblock` の引数はメモリ ブロックの開始を示します。  `memblock` が `NULL`の場合、\_`recalloc` は [calloc](../../c-runtime-library/reference/calloc.md) と同様に動作し、`num` \* `size` バイトの新しいブロックを割り当てます。  各要素は 0 に初期化されます。  `memblock` が `NULL`でない場合、`calloc`、[malloc](../../c-runtime-library/reference/malloc.md)、または [realloc](../../c-runtime-library/reference/realloc.md)に前の呼び出しによって返されるポインターのようになります。  
  
 新しいブロックは新しいメモリ位置になるため、\_`recalloc` で返されたポインターは `memblock` 引数を介して渡されたポインターであることは保証されません。  
  
 `_recalloc` は `ENOMEM` にメモリ割り当てが失敗した場合、または要求されているメモリの量を `_HEAP_MAXREQ`を超えた場合 `errno` を設定します。  これにより、およびそのほかのエラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 `recalloc` の 呼び出し `realloc` C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 関数を new ハンドラー モードを設定するために使用します。  新しいハンドラー モードは、エラーが発生したときに、`realloc` が [\_set\_new\_handler](../Topic/_set_new_handler.md) によって設定された新しいハンドラー ルーチンを呼び出すかどうかを指定します。  既定では、`realloc` は、メモリの割り当てエラーの際に新しいハンドラー ルーチンを呼び出しません。  同じ理由で失敗すると `new` の演算子は、\_`recalloc` がメモリを割り当てると、`realloc` が new ハンドラー ルーチンを同じ方法で呼び出すように、既定の動作をオーバーライドできます。  既定の動作をオーバーライドするには、次の関数を呼び出します。  
  
```  
_set_new_mode(1)  
```  
  
 高速 NEWMODE.OBJ のプログラム、またはリンクです。  
  
 アプリケーションが C ランタイム ライブラリのデバッグ バージョンとリンクすると、\_`recalloc` は [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)に解決されます。  ヒープのデバッグ中にどのように管理されるかを詳細については、「[CRT のデバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
 `_recalloc` は グローバル変数を変更せずに関数が保証され、返されたポインターが、エイリアス化されたことを意味するマークされた `__declspec(noalias)` と `__declspec(restrict)`です。  詳細については、「[noalias](../../cpp/noalias.md) と [restrict](../../cpp/restrict.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_recalloc`|\<stdlib.h\> および \<malloc.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [リンク オプション](../Topic/Link%20Options.md)