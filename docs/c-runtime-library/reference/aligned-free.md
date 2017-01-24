---
title: "_aligned_free | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_free"
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
  - "aligned_free"
  - "_aligned_free"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_free 関数"
  - "aligned_free 関数"
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)で割り当てられたメモリ ブロックを解放します。  
  
## 構文  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### パラメーター  
 `memblock`  
 `_aligned_malloc` または `_aligned_offset_malloc` 関数に返されたメモリ ブロックへのポインター。  
  
## 解説  
 `_aligned_free` は グローバル変数を変更せずに関数が保証されることを意味するマークされた `__declspec(noalias)`です。  詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。  
  
 この関数は、他の\_aligned CRT 関数とは異なり、パラメーターを検証しません。  `memblock` が `NULL` のポインターの場合、この関数は操作を実行しません。  これは `errno` は変更されず、無効なパラメーター ハンドラーは呼び出されません。  エラーがメモリ ブロックを割り当てること\_aligned 関数を使用しない、関数の前に発生するやメモリのミスアラインメントが予測災害が原因で発生する場合、関数は [\_RPT、\_RPTF、\_RPTW、\_RPTFW のマクロ](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)からデバッグのレポートが生成されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_free`|\<malloc.h\>|  
  
## 使用例  
 詳細については、「[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データの整列](../../c-runtime-library/data-alignment.md)