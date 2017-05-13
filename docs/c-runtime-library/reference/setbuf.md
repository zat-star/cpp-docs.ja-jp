---
title: setbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setbuf
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
- setbuf
dev_langs:
- C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
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
ms.openlocfilehash: 2fee25a696156136b7ef61402282a5e22ae31d05
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="setbuf"></a>setbuf
ストリーム バッファリングを制御します。 この関数は使用されなくなりました。代わりに [setvbuf](../../c-runtime-library/reference/setvbuf.md) をご使用ください。  
  
## <a name="syntax"></a>構文  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `buffer`  
 ユーザー割り当てのバッファー。  
  
## <a name="remarks"></a>コメント  
 `setbuf` 関数は `stream` のバッファリングを制御します。 `stream` 引数は、読み取りも書き込みもされていないオープン ファイルを指す必要があります。 `buffer` 引数が `NULL` である場合、ストリームはバッファー処理されません。 そうでない場合には、バッファーは長さ `BUFSIZ` の文字配列を指す必要があります。ここで、`BUFSIZ` は STDIO.H で定義されているバッファー サイズです。 所定のストリームに対してシステムによって割り当てられた既定のバッファーではなく、ユーザーが指定したバッファーが I/O バッファー処理に使用されます。 `stderr` ストリームは既定ではバッファー処理されませんが、`setbuf` を使用して `stderr` にバッファーを割り当てることができます。  
  
 `setbuf` は [setvbuf](../../c-runtime-library/reference/setvbuf.md) によって置き換えられました。これは新しいコード用の優先ルーチンです。 `setbuf` では、既存のコードとの互換性が保持されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
stream1 set to user-defined buffer at: 0012FCDC  
stream2 buffering disabled  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
