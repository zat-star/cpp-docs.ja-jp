---
title: _read | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _read
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
- _read
dev_langs:
- C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad5b18300ec36cc55a6eb02476b454829193cd8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="read"></a>_read

ファイルからデータを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
### <a name="parameters"></a>パラメーター  

*fd*  
開いているファイルを参照するファイル記述子。  
  
*バッファー*  
データの格納場所。  
  
*count*  
最大バイト数。  
  
## <a name="return-value"></a>戻り値  

`_read` 小さい場合があります、読み取られたバイト数を返しますより*カウント*よりも少ない場合*カウント*ファイル内の残りのバイト数またはその場合は、ファイルがテキスト モードで開かれた場合と、各キャリッジ リターンとライン フィードのペア`\r\n`は 1 つの改行文字に置き換えられます`\n`です。 戻り値ではその単一の改行文字だけがカウントされます。 この置き換えは、ファイル ポインターには影響しません。  
  
この関数はファイルの終わりで読み取りをすると、0 を返します。 場合*fd*は無効ですが、ファイルが開いていないを読み取り、またはファイルがロックされているで説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数は -1 を返し、 `errno` を `EBADF`に設定します。  
  
*バッファー*が **NULL** の場合は、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、 `errno` は `EINVAL` に設定されます。  
  
このリターン コードとその他のリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  

`_read`関数は、最大数を読み取ります*カウント*にバイト*バッファー*に関連付けられているファイルから*fd*です。 読み取り操作は、指定されたファイルに関連付けられたファイル ポインターの現在の位置で開始されます。 読み取り操作後、ファイル ポインターは、次の未読の文字を指します。  
  
ファイルがテキスト モードで開かれた場合、ファイルの終わりを示すインジケーターとして扱われる CTRL + Z の文字が `_read` で検出された時点で、読み取りは終了します。 ファイルの終わりのインジケーターをクリアするには、[_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) を使用します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```C  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
### <a name="input-crtreadtxt"></a>入力: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>出力  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>参照  

[下位入出力](../../c-runtime-library/low-level-i-o.md)   
[_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[fread](../../c-runtime-library/reference/fread.md)   
[_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
[_write](../../c-runtime-library/reference/write.md)
