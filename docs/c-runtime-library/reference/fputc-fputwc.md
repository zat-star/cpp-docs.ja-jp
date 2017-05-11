---
title: "fputc、fputwc | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fputc
- fputwc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fputc
- fputwc
- _fputtc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7eb1bb55bd153f4ef5387b616b72f611e3a50a9f
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fputc-fputwc"></a>fputc、fputwc
ストリームに文字を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 書き込む文字。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、書き込まれた文字を返します。 `fputc` の場合、`EOF` の戻り値はエラーを示します。 `fputwc` の場合、`WEOF` の戻り値はエラーを示します。 `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらは `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、関連付けられたファイル位置指示子によって示された位置のファイルに単一の文字 `c` を書き込み (定義されている場合)、必要に応じて指示子を進めます。 場合、`fputc`と`fputwc`、ファイルに関連付けられている`stream`です。 ファイルが配置要求をサポートできない場合、または追加モードでファイルが開かれた場合、文字はストリームの末尾に追加されます。  
  
 ストリームが ANSI モードで開かれている場合、2 つの関数の動作は同じになります。 `fputc` では、UNICODE ストリームへの出力はサポートされていません。  
  
 `_nolock` サフィックス付きのバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 詳細については、「[_fputc_nolock、_fputwc_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md)」を参照してください。  
  
 ルーチン固有の解説は、次のとおりです。  
  
|ルーチン|コメント|  
|-------------|-------------|  
|`fputc`|`putc` と同じですが、関数とマクロではなく関数としてのみ実装されています。|  
|`fputwc`|`fputc` のワイド文字バージョン。 `c` がテキスト モードまたはバイナリ モードで開かれるかどうかに従って、マルチバイト文字またはワイド文字として `stream` を書き込みます。|  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fputc`|\<stdio.h>|  
|`fputwc`|\<stdio.h> または \<wchar.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
```Output  
This is a test of fputc!!  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetc、fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)
