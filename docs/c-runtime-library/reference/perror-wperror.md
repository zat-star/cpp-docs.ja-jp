---
title: "perror、_wperror | Microsoft Docs"
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
  - "_wperror"
  - "perror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wperror"
  - "_tperror"
  - "perror"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tperror 関数"
  - "_wperror 関数"
  - "エラー メッセージ, 印刷"
  - "perror 関数"
  - "出力 (エラー メッセージを)"
  - "tperror 関数"
  - "wperror 関数"
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# perror、_wperror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー メッセージを表示します。  
  
## 構文  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### パラメーター  
 `string`  
 印刷する文字列メッセージ。  
  
## 解説  
 `perror` 関数は `stderr`にエラー メッセージが出力されます。  `_wperror` は **\_perror**のワイド文字バージョンであり、; `_wperror` への `string` の引数はワイド文字列です。  `_wperror` と **\_perror** は別の方法で同様に動作します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string`、コロン、およびエラーを生成し、最終的に改行文字で、その後に最初に出力される最後のライブラリの呼び出しのシステム エラー メッセージ。  `string` が null 文字列に null ポインターまたはポインターの場合、`perror` はシステム エラー メッセージだけを印刷します。  
  
 エラー数が変数に格納されます。[errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) ERRNO.H\) で定義されます。  システム エラー メッセージは、エラー番号順のメッセージの配列である変数 [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を使用してアクセスできます。  `perror` は `_sys_errlist`にインデックスとして `errno` 値を使用して適切なエラー メッセージが出力されます。  変数 [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) の値は、`_sys_errlist` の配列の要素の最大数として定義されます。  
  
 正確な結果を得るために、ライブラリ ルーチンの直後の呼び出し `perror` はエラーが返されます。  それ以外の以降の呼び出しでは `errno` 値を上書きします。  
  
 Windows オペレーティング システムでは、ERRNO.H に示されている `errno` の値は使用されません。  これらの値は、UNIX のオペレーティング システムで使用するために予約されています。  Windows オペレーティング システムで使用される `errno` 値のリスティングの [" \_doserrno、errno、\_sys\_errlist、および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を参照してください。  `perror` は これらのプラットフォームで使用されていない `errno` 値ごとに空の文字列を出力します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`perror`|\<stdio.h または\> stdlib.h \<\>|  
|`_wperror`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## 出力  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror、\_strerror、\_wcserror、\_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)