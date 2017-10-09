---
title: "_futime、_futime32、_futime64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- futime
- _futime
- futime64
- _futime64
dev_langs:
- C++
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 03eda993cbc087d5dc39f2c9d0f985ac5db48099
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="futime-futime32-futime64"></a>_futime、_futime32、_futime64
開いているファイルの変更時刻を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルのファイル記述子。  
  
 `filetime`  
 新しい変更日を含む構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 処理が正常に終了した場合は 0 を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は-1 を返しますと`errno`に設定されている`EBADF`、無効なファイル記述子、ことを示すまたは`EINVAL`、無効なパラメーターを示すです。  
  
## <a name="remarks"></a>コメント  
 `_futime`ルーチンに関連付けられている、開いているファイルで、変更日時、アクセスを設定する`fd`です。 `_futime` は [_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) と同じですが、引数が、ファイルの名前またはファイルへのパスではなく開いているファイルのファイル記述子である点が異なります。 `_utimbuf` 構造体には、新しい変更日とアクセス時間のフィールドが含まれています。 両方のフィールドに、有効な値が含まれている必要があります。 `_utimbuf32` および `_utimbuf64` は `_utimbuf` と同じですが、それぞれを 32 ビットおよび 64 ビットの時刻の型を使用する点が異なります。 `_futime` および `_utimbuf` は、64 ビット時刻型を使用し、`_futime` の動作は `_futime64` と同じです。 古い動作を強制的に実行させる必要がある場合は、`_USE_32BIT_TIME_T` を定義します。 これにより、`_futime` の動作が `_futime32` と同じになり、`_utimbuf` 構造帯が、32 ビットの時間型を使用し、`__utimbuf32` と等しくなります。  
  
 `__utimbuf64` 構造体を使用する `_futime64` は、UTC の 3000 年 12 月 31 日 23時 59分: 59 秒までのファイル日付を読み取りおよび変更できますが、これに対して `_futime32` の呼び出しは、ファイルの日付が UTC の 2038 年 1 月 18 日 23 時 59分: 59 秒よりも後の場合は失敗します。 これらの関数の日付範囲の下限は、1970 年 1 月 1 日の午前 0 時です。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`_futime`|\<sys/utime.h>|\<errno.h>|  
|`_futime32`|\<sys/utime.h>|\<errno.h>|  
|`_futime64`|\<sys/utime.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## <a name="input-crtfutimecinput"></a>Input: crt_futime.c_input  
  
```  
Arbitrary file contents.  
```  
  
### <a name="sample-output"></a>出力例  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)
