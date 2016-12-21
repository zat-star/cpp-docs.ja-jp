---
title: "_dupenv_s_dbg、_wdupenv_s_dbg | Microsoft Docs"
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
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
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
  - "_tdupenv_s_dbg"
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tdupenv_s_dbg 関数"
  - "dupenv_s_dbg 関数"
  - "_wdupenv_s_dbg 関数"
  - "環境変数"
  - "tdupenv_s_dbg 関数"
  - "wdupenv_s_dbg 関数"
  - "_dupenv_s_dbg 関数"
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _dupenv_s_dbg、_wdupenv_s_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の環境から値を取得します。追加のデバッグ情報を提供するために [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) でメモリを割り当てる、[\_dupenv\_s、\_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md) のバージョン。  
  
## 構文  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### パラメーター  
 `buffer`  
 変数の値を格納するバッファー。  
  
 `numberOfElements`  
 `buffer` のサイズ。  
  
 `varname`  
 環境変数名。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 ソース ファイルの名前へのポインター、または `NULL`。  
  
 `linenumber`  
 ソース ファイル内の行番号、または `NULL`。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
 これらの関数は、パラメーターを検証します。`buffer` または `varname` が `NULL` の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 十分なメモリを割り当てられない場合、これらの関数は `buffer` を `NULL` に、`numberOfElements` を 0 に設定し、`ENOMEM` を返します。  
  
## 解説  
 `_dupenv_s_dbg` および `_wdupenv_s_dbg` 関数は `_dupenv_s` および `_wdupenv_s` と同じものですが、`_DEBUG` が定義されている場合に、これらの関数は環境変数の値にメモリを割り当てるために [malloc](../../c-runtime-library/reference/malloc.md) および [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) のデバッグ バージョンを使用する点が異なります。  `_malloc_dbg` のデバッグ機能の詳細については、「[\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)」を参照してください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。  代わりに、フラグ `_CRTDBG_MAP_ALLOC` を定義することができます。  `_CRTDBG_MAP_ALLOC` が定義されている場合、`_dupenv_s` および `_wdupenv_s` の呼び出しはそれぞれ `_dupenv_s_dbg` および `_wdupenv_s_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。  そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。  ブロック型の詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_dupenv_s_dbg`|\<crtdbg.h\>|  
|`_wdupenv_s_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## 出力例  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## 同等の .NET Framework 関数  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [環境定数](../../c-runtime-library/environmental-constants.md)   
 [getenv\_s、\_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s、\_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)