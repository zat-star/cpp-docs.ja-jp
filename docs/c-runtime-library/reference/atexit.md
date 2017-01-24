---
title: "atexit | Microsoft Docs"
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
  - "atexit"
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
  - "atexit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "atexit 関数"
  - "処理, 終了時"
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atexit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

終了時に指定された関数を処理します。  
  
## 構文  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### パラメーター  
 `func`  
 呼び出される関数。  
  
## 戻り値  
 `atexit` でエラーが発生した場合、または 0 以外の値正常終了した場合は 0 を返します。  
  
## 解説  
 `atexit` 関数は、プログラムが正常に終了した場合に呼び出す関数 \(`func`\) のアドレスに渡されます。  `atexit` に継続的に呼び出し、最後に実行される関数のレジスタ、\(LIFO\) 最初のシーケンスを作成します。  `atexit` に渡された関数はパラメーターを使用できません。  `atexit` と `_onexit` は関数のレジスタを、ヒープを使用します。  したがって、登録できる関数の数はヒープ メモリでのみ使用できます。  
  
 `atexit` 関数のコードは `atexit` 関数が呼び出されるときに既にアンロードされた可能性のある DLL 依存関係を含めることはできません。  
  
 \(`_onexit` の同様の関数\) ではなく ANSI 準拠アプリケーションを生成するには、`atexit` の ANSI 標準関数を使用します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`atexit`|\<stdlib.h\>|  
  
## 使用例  
 このプログラムは `atexit` が呼び出されたときに実行する関数のスタックに 4 個の関数を押します。  プログラムの終了が最後に、これらのプログラムを実行すると、最初に基本。  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
  **これが最初に実行されます。**  
**これにより、次に実行されます。**   
## 同等の .NET Framework 関数  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit、\_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)