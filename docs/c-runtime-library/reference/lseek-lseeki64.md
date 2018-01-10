---
title: "_lseek、_lseeki64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lseeki64
- _lseek
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
- _lseeki64
- _lseek
- lseeki64
dev_langs: C++
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4dad9abf8b82cc5c6e876af22a1a2f61a6216ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lseek-lseeki64"></a>_lseek、_lseeki64
指定した場所にファイル ポインターを移動します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      long _lseek(  
   int fd,  
   long offset,  
   int origin   
);  
__int64 _lseeki64(  
   int fd,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 *オフセット*  
 *配信元*からのバイト数。  
  
 *配信元*  
 最初の位置。  
  
## <a name="return-value"></a>戻り値  
 `_lseek` は、ファイルの先頭からの新しい位置のオフセットを、バイト単位で返します。 `_lseeki64` は、64 ビット整数のオフセットを返します。 この関数は、エラーを示す-1 L を返します。 不適切なファイル記述子、*origin* の値が無効、*オフセット*によって指定された位置がファイルの開始より前であるなど、無効なパラメーターが渡された場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明にあるとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EBADF` に設定し、-1L を返します。 (ターミナルやポインターなどの) シーク非対応のデバイスでは、戻り値は未定義です。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_lseek` 関数は、`fd` に関連付けられたファイル ポインターを *origin* から*オフセット* バイトの新しい場所に移動します。 ファイルの次の操作は、新しい場所で行われます。 *origin* 引数は、Stdio.h で定義されている、次の定数のいずれかである必要があります。  
  
 `SEEK_SET`  
 ファイルの先頭。  
  
 `SEEK_CUR`  
 ファイル ポインターの現在の位置。  
  
 `SEEK_END`  
 ファイルの終わり。  
  
 `_lseek` を使用して、ポインターをファイルの任意の場所またはファイルの最後の後に移動することができます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_lseek`|\<io.h>|  
|`_lseeki64`|\<io.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_lseek.c  
/* This program first opens a file named lseek.txt.  
 * It then uses _lseek to find the beginning of the file,  
 * to find the current position in the file, and to find  
 * the end of the file.  
 */  
  
#include <io.h>  
#include <fcntl.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh;  
   long pos;               /* Position of file pointer */  
   char buffer[10];  
  
   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );  
  
   /* Seek the beginning of the file: */  
   pos = _lseek( fh, 0L, SEEK_SET );  
   if( pos == -1L )  
      perror( "_lseek to beginning failed" );  
   else  
      printf( "Position for beginning of file seek = %ld\n", pos );  
  
   /* Move file pointer a little */  
    _read( fh, buffer, 10 );  
  
   /* Find current position: */  
   pos = _lseek( fh, 0L, SEEK_CUR );  
   if( pos == -1L )  
      perror( "_lseek to current position failed" );  
   else  
      printf( "Position for current position seek = %ld\n", pos );  
  
   /* Set the end of the file: */  
   pos = _lseek( fh, 0L, SEEK_END );  
   if( pos == -1L )  
      perror( "_lseek to end failed" );  
   else  
      printf( "Position for end of file seek = %ld\n", pos );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlseekcinput"></a>入力: crt_lseek.c_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## <a name="output"></a>出力  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## <a name="see-also"></a>参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_tell、_telli64](../../c-runtime-library/reference/tell-telli64.md)