---
title: clearerr_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clearerr_s
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
- clearerr_s
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr_s function
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5bdd1bacddfa22bb9a7fe7b3d6e11b06c5a969b6
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="clearerrs"></a>clearerr_s
ストリームのエラー インジケーターをリセットします。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [clearerr](../../c-runtime-library/reference/clearerr.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t clearerr_s(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0、`stream` が NULL の場合は `EINVAL`。  
  
## <a name="remarks"></a>コメント  
 `clearerr_s` 関数は、`stream` のエラー インジケーターとファイルの終わりインジケーターをリセットします。 エラー インジケーターは自動的にクリアされません。指定のストリームのエラー インジケーターを設定すると、そのストリームに対する操作は、`clearerr_s`、`clearerr`、`fseek`、`fsetpos`、または `rewind` が呼び出されるまでエラー値を返し続けます。  
  
 `stream` が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`clearerr_s`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_clearerr_s.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   errno_t err;  
  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
}  
```  
  
```Output  
  
n  
  
```  
  
```Output  
  
      nWrite error: Bad file descriptor  
Will input cause an error? n  
```  
  
## <a name="see-also"></a>関連項目  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、_wperror](../../c-runtime-library/reference/perror-wperror.md)
