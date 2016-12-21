---
title: "_heapmin | Microsoft Docs"
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
  - "_heapmin"
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
  - "_heapmin"
  - "heapmin"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapmin 関数"
  - "ヒープ メモリ"
  - "heapmin 関数"
  - "ヒープ, 解放 (未使用のメモリを)"
  - "メモリ, 解放"
  - "最小化 (ヒープを)"
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapmin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オペレーティング システムの未使用のヒープ メモリを解放します。  
  
## 構文  
  
```  
int _heapmin( void );  
```  
  
## 戻り値  
 、`_heapmin` の正常終了した場合は 0; そうしないと、関数の戻り値–1 と `ENOSYS`に設定 `errno`。  
  
 これにより、他のリターン コードに関する詳細については、「[" \_doserrno、errno、\_sys\_errlist、および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_heapmin` 関数は、オペレーティング システムに未使用のヒープ メモリを解放することによって、ヒープを最小化します。  オペレーティング システムが `_heapmin` \(たとえば、Windows 98\) をサポートする、関数の戻り値–1 は `ENOSYS`に `errno` を設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_heapmin`|\<malloc.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [メモリ割り当て](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../Topic/_heapwalk.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)