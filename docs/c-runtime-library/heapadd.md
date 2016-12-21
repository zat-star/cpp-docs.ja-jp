---
title: "_heapadd | Microsoft Docs"
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
  - "_heapadd"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "heapadd"
  - "_heapadd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapadd 関数"
  - "heapadd 関数"
  - "ヒープ, 追加 (メモリを)"
  - "メモリ, 追加 (ヒープに)"
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapadd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヒープにメモリを追加します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降では、CRT で使用できません。  
  
## 構文  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### パラメーター  
 `memblock`  
 ヒープ メモリへのポインター。  
  
 `size`  
 追加するメモリのサイズ \(バイト単位\)。  
  
## 戻り値  
 成功すると、`_heapadd` は 0 を返します。それ以外の場合、この関数は \-1 を返し、`errno` を `ENOSYS` に設定します。  
  
 このリターン コードとその他のリターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 Visual C\+\+ のバージョン 4.0 以降では、新しいデバッグ機能をサポートするために、基になるヒープ構造が C ランタイム ライブラリに移動しました。 その結果、`_heapadd` は、Win32 API に基づいているすべてのプラットフォームでサポートされなくなりました。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_heapadd`|\<malloc.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../Topic/_heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)