---
title: "_aligned_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_recalloc"
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
  - "aligned_recalloc"
  - "_aligned_recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_recalloc 関数"
  - "_aligned_recalloc 関数"
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリに変更し、0 を初期化しますメモリ ブロックのサイズを返します。  
  
## 構文  
  
```  
void * _aligned_recalloc(  
   void *memblock,   
   size_t num,  
   size_t size,   
   size_t alignment  
);  
```  
  
#### パラメーター  
 \[入力\] `memblock`  
 現在のメモリ ブロックのポインター。  
  
 \[入力\] `num`  
 要素の数。  
  
 \[入力\] `size`  
 各要素のサイズ \(バイト単位\)。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
## 戻り値  
 `_aligned_recalloc` が 再割り当てされる場合 \(移動\) メモリ ブロックの void なポインターを返します。  戻り値は、buffer 引数が `NULL`である場合、または特定のサイズにブロックを展開する十分な使用可能なメモリがサイズがゼロである場合 `NULL` です。  最初のケースでは、元のブロックが解除されます。  2 番目の例では、元のブロックは変更されません。  戻り値は適切にどの型のオブジェクトを格納するために配置されることが保証されるストレージ領域を指します。  void 以外の型へのポインターを取得するには、戻り値の型キャストを使用してください。  
  
 これは、メモリの再割り当てされ、ブロックの配置を変更するとエラーになります。  
  
## 解説  
 `_aligned_recalloc` は `malloc`に基づいています。  `_aligned_offset_malloc`の詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `_HEAP_MAXREQ` より大きかった場合に、`errno` を `ENOMEM` に設定します。  `errno` の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  また、`_aligned_recalloc` はそのパラメーターを検証します。  `alignment` が 2 の累乗でない場合、この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_recalloc`|\<malloc.h\>|  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データの整列](../../c-runtime-library/data-alignment.md)   
 [\_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)