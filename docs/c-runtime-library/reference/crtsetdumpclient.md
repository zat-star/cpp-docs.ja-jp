---
title: "_CrtSetDumpClient | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDumpClient"
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
  - "_CrtSetDumpClient"
  - "CrtSetDumpClient"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetDumpClient 関数"
  - "CrtSetDumpClient 関数"
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetDumpClient
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`_CLIENT_BLOCK` 型のメモリ ブロックをダンプするアプリケーション定義関数をインストールします \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### パラメーター  
 `dumpClient`  
 C ランタイム デバッグ メモリ ダンプ プロセスにフックする新しいクライアント定義メモリ ダンプ関数。  
  
## 戻り値  
 以前に定義されていたクライアント ブロック ダンプ関数を返します。  
  
## 解説  
 `_CrtSetDumpClient` 関数を使用すると、アプリケーションは独自の関数をフックして、`_CLIENT_BLOCK` メモリ ブロックに格納されているオブジェクトを C ランタイム デバッグのメモリ ダンプ プロセスにダンプすることができます。  その結果、[\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md) や [\_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) などのデバッグ ダンプ関数が `_CLIENT_BLOCK` メモリ ブロックをダンプするたびに、アプリケーションのダンプ関数も呼び出されます。  `_CrtSetDumpClient` を使用すると、アプリケーションは簡単にメモリ リークを検出したり、`_CLIENT_BLOCK` ブロックに格納されているデータの内容の検証やレポートを行うことができます。  [\_DEBUG](../Topic/_DEBUG.md) が未定義の場合、`_CrtSetDumpClient` の呼び出しはプリプロセスで削除されます。  
  
 `_CrtSetDumpClient` 関数は、`dumpClient` で指定された新しいアプリケーション定義ダンプ関数をインストールし、以前に定義されたダンプ関数を返します。  クライアント ブロック ダンプ関数の例は、次のとおりです。  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 `userPortion` 引数はメモリ ブロックのユーザー データ部分の先頭へのポインターであり、`blockSize` は割り当てられたメモリ ブロックのサイズをバイト単位で指定します。  クライアント ブロック ダンプ関数は、`void` を返す必要があります。  `_CrtSetDumpClient` に渡されるクライアント ダンプ関数へのポインターは、Crtdbg.h で次のように定義されているように、`_CRT_DUMP_CLIENT` 型です。  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 `_CLIENT_BLOCK` 型のメモリ ブロックを操作する関数の詳細については、「[Client ブロック用のフック関数](../Topic/Client%20Block%20Hook%20Functions.md)」を参照してください。  ブロックの型やその細分化された型に関する情報を返すには、[\_CrtReportBlockType](../Topic/_CrtReportBlockType.md) 関数を使用できます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtSetDumpClient`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)   
 [\_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)