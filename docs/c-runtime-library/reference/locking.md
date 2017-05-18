---
title: _locking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _locking
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
- _locking
dev_langs:
- C++
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 19
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7789a1634f5ee87d54d6b9f2aadbc720819f31ef
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="locking"></a>_locking
ファイルのバイトをロックまたはロック解除します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 ファイル記述子。  
  
 *モード*  
 実行するロック アクション。  
  
 *nbytes*  
 ロックするバイト数。  
  
## <a name="return-value"></a>戻り値  
 処理が正常に終了した場合、`_locking` は 0 を返します。 戻り値-1 が後者障害を示す[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)は、次の値のいずれかに設定します。  
  
 `EACCES`  
 ロック違反 (ファイルはすでにロックされている場合もロック解除されている場合もある)。  
  
 `EBADF`  
 無効なファイル記述子。  
  
 `EDEADLOCK`  
 ロック違反。 `_LK_LOCK` フラグまたは `_LK_RLCK` フラグが指定されていて、試行回数が 10 回を超えてもファイルをロックできない場合に返されます。  
  
 `EINVAL`  
 無効な引数が `_locking` に指定されました。  
  
 エラーの原因が無効なファイル記述子などの無効なパラメーターである場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  
  
## <a name="remarks"></a>コメント  
 `_locking` 関数は、`fd` によって指定されたファイルの *nbytes* バイトをロックまたはロック解除します。 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 すべてのロックまたはロック解除は、ファイル ポインターの現在の位置から開始され、次の *nbytes* バイトに進みます。 ファイルの終わりを超えてバイトをロックできます。  
  
 *mode* は、Locking.h で定義されている、次のマニフェスト定数のいずれかである必要があります。  
  
 `_LK_LOCK`  
 指定したバイトをロックします。 バイトをロックできない場合、プログラムによって 1 秒後に直ちに再試行されます。 10 回試行した後、バイトをロックできなかった場合、定数はエラーを返します。  
  
 `_LK_NBLCK`  
 指定したバイトをロックします。 バイトをロックできない場合、定数はエラーを返します。  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK` と同じ。  
  
 `_LK_RLCK`  
 `_LK_LOCK` と同じ。  
  
 `_LK_UNLCK`  
 指定したバイトのロックを解除します。バイトは既にロックされている必要があります。  
  
 重複しない、ファイルの複数の領域をロックできます。 ロック解除の対象領域は、既にロックされている必要があります。 `_locking` は隣接する領域をマージしません。2 つのロックされた領域が隣接している場合は、各領域を個別にロック解除する必要があります。 領域は短期間だけロックされ、ファイルを閉じる前またはプログラムを終了する前にはロックを解除する必要があります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_locking`|\<io.h> と \<sys/locking.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlockingtxt"></a>入力: crt_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_creatn、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)
