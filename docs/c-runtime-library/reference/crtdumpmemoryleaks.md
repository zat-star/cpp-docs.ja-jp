---
title: "_CrtDumpMemoryLeaks | Microsoft Docs"
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
  - "_CrtDumpMemoryLeaks"
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
  - "CRTDBG_LEAK_CHECK_DF"
  - "CRTDBG_CHECK_CRT_DF"
  - "_CRTDBG_LEAK_CHECK_DF"
  - "CrtDumpMemoryLeaks"
  - "_CrtDumpMemoryLeaks"
  - "_CRTDBG_CHECK_CRT_DF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtDumpMemoryLeaks 関数"
  - "CRTDBG_LEAK_CHECK_DF マクロ"
  - "_CRTDBG_LEAK_CHECK_DF マクロ"
  - "_CrtDumpMemoryLeaks 関数"
  - "CRTDBG_CHECK_CRT_DF マクロ"
  - "_CRTDBG_CHECK_CRT_DF マクロ"
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDumpMemoryLeaks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## 戻り値  
 `_CrtDumpMemoryLeaks` は、メモリ リークが見つかった場合は TRUE を返します。  それ以外の場合、関数は FALSE を返します。  
  
## 解説  
 `_CrtDumpMemoryLeaks` 関数は、プログラムの実行開始以降にメモリ リークが発生したかどうかを判定します。  メモリ リークが見つかると、ヒープ内のすべてのオブジェクトのデバッグ ヘッダー情報が、ユーザーが判読できる形式でダンプされます。  [\_DEBUG](../Topic/_DEBUG.md) が未定義の場合、`_CrtDumpMemoryLeaks` の呼び出しはプリプロセスで削除されます。  
  
 `_CrtDumpMemoryLeaks` は、アプリケーションによって割り当てられたすべてのメモリが解放されたことを確認するために、プログラムの実行終了時に頻繁に呼び出されます。  プログラムの終了時にこの関数が自動的に呼び出されるようにするには、[\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して、[\_crtDbgFlag](../Topic/_crtDbgFlag.md) フラグの `_CRTDBG_LEAK_CHECK_DF` ビット フィールドをオンにします。  
  
 `_CrtDumpMemoryLeaks` は [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) を呼び出してヒープの現在の状態を取得し、解放されていないブロックの状態をスキャンします。  解放されていないブロックが見つかると、`_CrtDumpMemoryLeaks` は [\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md) を呼び出して、プログラムの実行開始以降にヒープに割り当てられたすべてのオブジェクトについての情報をダンプします。  
  
 既定では、内部 C ランタイム ブロック \(`_CRT_BLOCK`\) は、メモリ ダンプ操作に含まれません。  これらのブロックをリーク検出プロセスに含めるには、[\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して、`_crtDbgFlag` の `_CRTDBG_CHECK_CRT_DF` ビットをオンにします。  
  
 ヒープ状態関数と `_CrtMemState` 構造体の詳細については、「[ヒープの状態をレポートする関数](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)」を参照してください。  デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 使用例  
 `_CrtDumpMemoryLeaks` の使用例については、「[crt\_dbg1](http://msdn.microsoft.com/ja-jp/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)