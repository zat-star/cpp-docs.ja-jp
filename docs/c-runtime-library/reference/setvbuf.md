---
title: setvbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setvbuf
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
- setvbuf
dev_langs:
- C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
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
ms.openlocfilehash: 3955a2e5c2f0371c804f1b5a7374540ca8720339
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="setvbuf"></a>setvbuf
ストリームのバッファリングとバッファー サイズを制御します。  
  
## <a name="syntax"></a>構文  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `buffer`  
 ユーザー割り当てのバッファー。  
  
 `mode`  
 バッファリングのモード。  
  
 `size`  
 バイト単位のバッファー サイズ。 許容範囲: 2 <= `size` <= INT_MAX (2147483647)。 内部的に、`size` に指定された値は 2 の倍数に最も近い値に切り捨てられます。  
  
## <a name="return-value"></a>戻り値  
 処理が正常に終了した場合は 0 を返します。  
  
 `stream` が `NULL` である場合や、`mode` または `size` が有効な変更の範囲内にない場合には、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
 これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `setvbuf` 関数により、プログラムはバッファー処理と `stream` のバッファー サイズの両方を制御することができます。 `stream` は、開かれて以来 I/O 操作を実施されたことのない開いているファイルを参照する必要があります。 `buffer` が指し示す配列が `NULL` でない場合には、それがバッファーとして使用されます。その配列が `NULL` である場合、`setvbuf` は自動的に割り当てられるバッファーを使用し、その長さは `size` /2 * 2 バイトです。  
  
 モードは `_IOFBF`、`_IOLBF`、または `_IONBF` である必要があります。 `mode` が `_IOFBF` または `_IOLBF` である場合には、`size` がバッファーのサイズとして使用されます。 `mode` が `_IONBF` である場合には、ストリームはバッファー処理されず、`size` と `buffer` は無視されます。 `mode` の値とその意味は次のとおりです。  
  
 `_IOFBF`  
 フル バッファリングします。つまり、`buffer` はバッファーとして使用され、`size` はバッファーのサイズとして使用されます。 `buffer` が `NULL` である場合には、自動的に割り当てられる `size` バイトの長さのバッファーが使用されます。  
  
 `_IOLBF`  
 一部のシステムでは、行バッファリングします。 ただし、Win32 の動作は `_IOFBF` と同じで、フル バッファリングします。  
  
 `_IONBF`  
 `buffer` または `size` に関係なく、バッファーは使用されません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)
