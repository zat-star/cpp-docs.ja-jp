---
title: feof | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- feof
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
- feof
dev_langs:
- C++
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 345ebdff9733ac25bd3a42dc5a5465d501e1f28f
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="feof"></a>feof
ストリームのファイルの末尾をテストします。  
  
## <a name="syntax"></a>構文  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 読み取り操作でファイルの末尾を越えて読み取ろうとした場合、ファイルの`feof` 関数は 0 以外の値を返します。それ以外の場合は 0 を返します。 ストリーム ポインターが `NULL` の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、`errno` は `EINVAL` に設定され、`feof`は 0 を返します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `feof` ルーチン (関数とマクロの両方として実装されています) は、`stream` の終わりを越えたかどうかを確認します。 ファイルの末尾を越えると、ストリームが閉じるか、`rewind`、`fsetpos`、`fseek`、または `clearerr` が呼び出されるまで、読み取り操作はファイルの末尾インジケーターを返します。  
  
 たとえば、10 バイトが含まれるファイルで、ファイルから 10 バイトを読み取ると、`feof` は 0 を返します。これは、ファイル ポインターがファイルの末尾にあっても、末尾を越えて読み取ろうと試みなかったためです。 11 バイト目を読み取ろうとした場合にのみ、`feof` は 0 以外の値を返します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`feof`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfeoftxt"></a>入力: crt_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>出力  
  
```  
Number of bytes read = 19  
```  
  
## <a name="see-also"></a>関連項目  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、_wperror](../../c-runtime-library/reference/perror-wperror.md)
