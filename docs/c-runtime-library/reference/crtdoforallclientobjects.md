---
title: "_CrtDoForAllClientObjects | Microsoft Docs"
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
  - "_CrtDoForAllClientObjects"
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
  - "_CrtDoForAllClientObjects"
  - "CrtDoForAllClientObjects"
  - "crtdbg/_CrdDoForAllClientObjects"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtDoForAllClientObjects 関数"
  - "CrtDoForAllClientObjects 関数"
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDoForAllClientObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ内のすべての `_CLIENT_BLOCK` 型に対して、アプリケーションによって提供される関数を呼び出します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### パラメーター  
 `pfn`  
 アプリケーションによって提供された関数コールバック関数へのポインター。 この関数の最初のパラメーターは、データを指します。 2 番目のパラメーターは、`_CrtDoForAllClientObjects` の呼び出しに渡されるコンテキスト ポインターです。  
  
 `context`  
 アプリケーションによって提供される関数に渡す、アプリケーションによって提供されるコンテキストへのポインター。  
  
## 解説  
 `_CrtDoForAllClientObjects` 関数は、ヒープのリンク リストで `_CLIENT_BLOCK` 型のメモリ ブロックを検索し、この型のブロックがある場合は、アプリケーションによって提供される関数を呼び出します。 見つかったブロックと `context` パラメーターは、アプリケーションによって提供される関数に引数として渡されます。 デバッグ中に、アプリケーションはメモリを割り当てるためのデバッグ ヒープ関数を明示的に呼び出し、ブロックに `_CLIENT_BLOCK` ブロック型を割り当てるように指定することによって、割り当ての特定のグループを追跡できます。 これらのブロックは個別に追跡し、リーク検出やメモリ状態のレポート時に異なる方法で報告できます。  
  
 [\_crtDbgFlag](../Topic/_crtDbgFlag.md) フラグの `_CRTDBG_ALLOC_MEM_DF` ビット フィールドがオンでない場合、`_CrtDoForAllClientObjects` はすぐに制御を返します。[\_DEBUG](../Topic/_DEBUG.md) が定義されていない場合、`_CrtDoForAllClientObjects` の呼び出しは前処理で削除されます。  
  
 `_CLIENT_BLOCK` 型、およびこれを他のデバッグ関数で使用する方法について詳しくは、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」をご覧ください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」をご覧ください。  
  
 `pfn` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は [errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を `EINVAL` に設定して処理を戻します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h\>、\<errno.h\>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** ユニバーサル C ランタイム ライブラリのデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [ヒープの状態をレポートする関数](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)   
 [\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)