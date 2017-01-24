---
title: "_aligned_realloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_realloc"
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
  - "_aligned_realloc"
  - "aligned_realloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "aligned_realloc 関数"
  - "_aligned_realloc 関数"
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)で割り当てられたメモリ ブロックのサイズを変更します。  
  
## 構文  
  
```  
void * _aligned_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment  
);  
```  
  
#### パラメーター  
 \[入力\] `memblock`  
 現在のメモリ ブロックのポインター。  
  
 \[入力\] `size`  
 要求されたメモリ割り当てのサイズ。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
## 戻り値  
 `_aligned_realloc` が 再割り当てされる場合 \(移動\) メモリ ブロックの void なポインターを返します。  戻り値は、buffer 引数が `NULL`である場合、または特定のサイズにブロックを展開する十分な使用可能なメモリがサイズがゼロである場合 `NULL` です。  最初のケースでは、元のブロックが解除されます。  第 2 に、元のブロックは変更されません。  戻り値は適切にどの型のオブジェクトを格納するために配置されることが保証されるストレージ領域を指します。  void 以外の型へのポインターを取得するには、戻り値の型キャストを使用してください。  
  
 これは、メモリの再割り当てされ、ブロックの配置を変更するとエラーになります。  
  
## 解説  
 `_aligned_realloc` は `malloc`に基づいています。  `_aligned_offset_malloc`の詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `_HEAP_MAXREQ` より大きかった場合に、`errno` を `ENOMEM` に設定します。  `errno` の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  また、`_aligned_realloc` はそのパラメーターを検証します。  `alignment` が 2 の累乗でない場合、この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_realloc`|\<malloc.h\>|  
  
## 使用例  
 詳細については、「[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)」を参照してください。  
  
## 参照  
 [データの整列](../../c-runtime-library/data-alignment.md)