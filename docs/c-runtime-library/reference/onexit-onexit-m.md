---
title: "_onexit、_onexit_m | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_onexit"
  - "_onexit_m"
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
  - "_onexit"
  - "onexit_m"
  - "onexit"
  - "_onexit_m"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "onexit 関数"
  - "登録、登録 (exit ルーチンの)"
  - "_onexit_m 関数"
  - "onexit_m 関数"
  - "_onexit 関数"
  - "登録 (exit ルーチンの)"
  - "登録 (終了時に呼び出す)"
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _onexit、_onexit_m
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

終了時に呼び出されるルーチンを登録します。  
  
## 構文  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### パラメーター  
 `function`  
 終了時に呼び出す関数へのポインター。  
  
## 戻り値  
 `_onexit` は 関数への関数ポインターを格納する領域があるか `NULL` 成功したポインターを返します。  
  
## 解説  
 `_onexit` 関数は、プログラムが正常に終了した場合に呼び出す関数 \(`function`\) のアドレスに渡されます。  `_onexit` に継続的な呼び出しは LIFO \(後入れ先出し \(LIFO\)\) 順序で実行される関数のレジスタを作成します。  `_onexit` に渡された関数はパラメーターを使用できません。  
  
 ケースで `DllMain` が DLL\_PROCESS\_DETACH に呼び出された後 `_onexit` が DLL 内から呼び出される場合、ルーチン アンロードする DLL の `_onexit` の実行に登録されています。  
  
 `_onexit` は Microsoft 拡張機能です。  ANSI 互換では、[atexit](../../c-runtime-library/reference/atexit.md)を使用します。  関数の `_onexit_m` バージョンは混合モードに使用されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_onexit`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## 出力  
  
```  
This is executed first.  
This is executed next.  
```  
  
## 同等の .NET Framework 関数  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_\_dllonexit](../../c-runtime-library/dllonexit.md)