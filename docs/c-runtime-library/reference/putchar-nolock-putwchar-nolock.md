---
title: "_putchar_nolock、_putwchar_nolock | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putchar_nolock
- _putwchar_nolock
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
apitype: DLLExport
f1_keywords:
- putwchar_nolock
- _puttchar_nolock
- _putchar_nolock
- _putwchar_nolock
- putchar_nolock
dev_langs:
- C++
helpviewer_keywords:
- _puttchar_nolock function
- putchar_nolock function
- characters, writing
- standard output, writing to
- putwchar_nolock function
- _putchar_nolock function
- _putwchar_nolock function
- puttchar_nolock function
ms.assetid: 9ac68092-bfc3-4352-b486-c3e780220575
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e9e1667242d4b569543e0044b85c319b83ff88d9
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="putcharnolock-putwcharnolock"></a>_putchar_nolock、_putwchar_nolock
スレッドをロックせずに **stdout** に文字を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _putchar_nolock(  
   int c   
);  
wint_t _putwchar_nolock(  
   wchar_t c   
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 書き込む文字。  
  
## <a name="return-value"></a>戻り値  
 「**putchar、putwchar**」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 **putchar_nolock** と `_putwchar_nolock` は、他のスレッドによる干渉から保護されない点を除いて **_nolock** のサフィックスがないバージョンと同じものです。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_puttchar_nolock`|`_putchar_nolock`|`_putchar_nolock`|`_putwchar_nolock`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_putchar_nolock`|\<stdio.h>|  
|`_putwchar_nolock`|\<stdio.h> または \<wchar.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_putchar_nolock.c  
/* This program uses putchar to write buffer  
 * to stdout. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = _putchar_nolock( *p );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [fgetc、fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)
