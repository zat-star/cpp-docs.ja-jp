---
title: _chsize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chsize
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
f1_keywords: _chsize
dev_langs: C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c48c9978650dc88ff2579a2838faf9bcb02cefa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chsize"></a>_chsize
ファイル サイズを変更します。 セキュリティが強化されたバージョンについては、「[_chsize_s](../../c-runtime-library/reference/chsize-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 `size`  
 バイト単位のファイルの新しい長さ。  
  
## <a name="return-value"></a>戻り値  
 ファイル サイズが正常に変更された場合は、`_chsize` は値 0 を返します。 戻り値-1 はエラーを示します:`errno`に設定されている`EACCES`かどうか、指定したファイルがロックされている、アクセスに対してに`EBADF`、指定したファイルは読み取り専用または記述子が有効でない場合`ENOSPC`デバイス、またはに領域が残っていない場合`EINVAL`場合`size`が 0 未満です。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_chsize` 関数は、`fd` に関連付けられているファイルを `size` に指定された長さに拡張するか切り捨てます。 ファイルは、書き込みを許可するモードで開かれている必要があります。 ファイルが拡張される場合は、null 文字 ('\0') が追加されます。 ファイルが切り捨てられる場合、短くなったファイルの末尾からファイルの元の長さまでのすべてのデータは失われます。  
  
 この関数は、パラメーターを検証します。 `size` が 0 未満か `fd` が正しくないファイル記述子である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_chsize`|\<io.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
```Output  
File length before: 0  
Size successfully changed  
File length after:  329678  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_sopen、_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)