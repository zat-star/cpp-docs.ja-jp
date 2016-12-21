---
title: "_aligned_offset_malloc | Microsoft Docs"
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
  - "_aligned_offset_malloc"
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
  - "_aligned_offset_malloc"
  - "aligned_offset_malloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_offset_malloc 関数"
  - "aligned_offset_malloc 関数"
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された配置境界にメモリを割り当てます。  
  
## 構文  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### パラメーター  
 \[入力\] `size`  
 要求されたメモリ割り当てのサイズ。  
  
 \[入力\] `alignment`  
 アラインメント値。2 の整数乗である必要があります。  
  
 \[入力\] `offset`  
 アラインメントを強制するためのメモリ割り当てへのオフセット。  
  
## 戻り値  
 割り当てられたメモリ ブロックへのポインター。操作が失敗した場合は 。  
  
## 解説  
 `_aligned_offset_malloc` は、入れ子になった要素に対するアラインメントが必要な状況で便利です。たとえば、入れ子になったクラスに対するアラインメントが必要になった場合などです。  
  
 `_aligned_offset_malloc` は `malloc` を基盤にしています。詳細については、「[malloc](../../c-runtime-library/reference/malloc.md)」を参照してください。  
  
 `_aligned_offset_malloc` は グローバル変数を変更せずに関数が保証され、返されたポインターが、エイリアス化されたことを意味するマークされた `__declspec(noalias)` と `__declspec(restrict)`です。  詳細については、「[noalias](../../cpp/noalias.md) と [restrict](../../cpp/restrict.md)」を参照してください。  
  
 この関数は、メモリ割り当てが失敗するか、要求されたサイズが `_HEAP_MAXREQ` より大きかった場合に、`errno` を `ENOMEM` に設定します。  `errno` の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  また、`_aligned_offset_malloc` はそのパラメーターを検証します。  `alignment` が 2 の累乗でないか、`offset` が `size` 以上で 0 以外である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_offset_malloc`|\<malloc.h\>|  
  
## 使用例  
 詳細については、「[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)」を参照してください。  
  
## 参照  
 [データの整列](../../c-runtime-library/data-alignment.md)