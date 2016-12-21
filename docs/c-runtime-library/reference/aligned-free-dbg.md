---
title: "_aligned_free_dbg | Microsoft Docs"
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
  - "_aligned_free_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_aligned_free_dbg"
  - "aligned_free_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free_dbg 関数"
  - "aligned_free_dbg 関数"
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) または [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) で割り当てられたメモリ ブロックを解放します \(デバッグのみ\)。  
  
## 構文  
  
```  
void _aligned_free_dbg(    void *memblock );  
```  
  
#### パラメーター  
 `memblock`  
 `_aligned_malloc` または `_aligned_offset_malloc` 関数に返されたメモリ ブロックへのポインター。  
  
## 解説  
 `_aligned_free_dbg` 関数は、[\_aligned\_free](../../c-runtime-library/reference/aligned-free.md) 関数のデバッグ バージョンです。  [\_DEBUG](../Topic/_DEBUG.md) が定義されない場合、`_aligned_free_dbg` への各呼び出しは \_`aligned_free` への呼び出しになります。  \_`aligned_free` と `_aligned_free_dbg` は、どちらもベース ヒープのメモリ ブロックを解放しますが、`_aligned_free_dbg` はデバッグ機能を提供します。解放されたブロックをヒープのリンク リストに保持してメモリ不足の状況をシミュレートする機能です。  
  
 `_aligned_free_dbg` は、解放操作を実行する前に、指定されたすべてのファイルおよびブロックの位置の有効性チェックを実行します。  アプリケーションは、この情報を提供する必要はありません。  メモリ ブロックが解放されると、デバッグ ヒープ マネージャーはユーザー部分の前後のバッファーの整合性を自動的にチェックし、それらのバッファーが上書きされていた場合はエラー レポートを発行します。  [\_crtDbgFlag](../Topic/_crtDbgFlag.md) フラグの `_CRTDBG_DELAY_FREE_MEM_DF` ビット フィールドが設定されている場合、解放されたブロックは値 0xDD 値を設定され、`_FREE_BLOCK` ブロック型を割り当てられ、ヒープのメモリ ブロックのリンク リストに保持されます。  
  
 メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  割り当てブロックの種類とそれらの使用方法の詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  アプリケーションのデバッグ ビルドで標準ヒープ関数を呼び出す場合とデバッグ バージョンを呼び出す場合との違いについては、「[デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_aligned_free_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)