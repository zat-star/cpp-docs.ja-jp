---
title: "_flushall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_flushall"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_flushall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flushall 関数"
  - "フラッシュ (ストリームを)"
  - "ストリーム、フラッシュ"
  - "_flushall 関数"
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _flushall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべてのストリームをフラッシュし、すべてのバッファーをクリアします。  
  
## 構文  
  
```  
int _flushall( void );  
```  
  
## 戻り値  
 `_flushall` は、開いているストリーム \(入力と出力\) の数を返します。  エラーの戻り値はありません。  
  
## 解説  
 既定では、`_flushall` 関数は、開いている出力ストリームに関連付けられているすべてのバッファーの内容を適切なファイルに書き込みます。  開いている入力ストリームに関連付けられているすべてのバッファーでは、現在の内容がクリアされます。これらのバッファーは通常はオペレーティング システムによって保持され、データをディスクに自動的に書き込むための最適なタイミングが決定されます。タイミングとしては、バッファーがいっぱいになったとき、ストリームが閉じられるとき、プログラムがストリームを閉じずに正常に終了したときがあります。  
  
 読み取りの後に `_flushall` が呼び出されると、新しいデータが入力ファイルからバッファーに読み込まれます。  すべてのストリームは、`_flushall` の呼び出し後、開いたままになります。  
  
 ランタイム ライブラリのディスクへのコミットの機能を使用すると、重要なデータをオペレーティング システムのバッファーではなく、ディスクに直接書き込むことができます。  プログラムのオブジェクト ファイルを Commode.obj にリンクすると、既存のプログラムを書き直さずに、この機能を有効にできます。  そのようにした実行可能ファイルでは、`_flushall` を呼び出すと、すべてのバッファーの内容がディスクに書き込まれます。  `_flushall` と `fflush` だけが、Commode.obj の影響を受けます。  
  
 ディスクへのコミットの機能の制御については、「[ストリーム入出力](../../c-runtime-library/stream-i-o.md)」、「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」、および「[\_fdopen](../Topic/_fdopen,%20_wfdopen.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_flushall`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
  **There were 3 streams flushed**   
## 同等の .NET Framework 関数  
  
-   [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
-   [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)  
  
-   [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)  
  
-   [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_commit](../../c-runtime-library/reference/commit.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../Topic/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)