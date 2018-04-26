---
title: setbuf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 7a88ac98b8226b51ad036a0e31c919db9a63a0a0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="setbuf"></a>setbuf

ストリーム バッファリングを制御します。 この関数は非推奨とされました。代わりに [setvbuf](setvbuf.md) をご使用ください。

## <a name="syntax"></a>構文

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*へのポインター**ファイル**構造体。

*バッファー*ユーザーに割り当てられたバッファー。

## <a name="remarks"></a>コメント

**Setbuf**関数のコントロールでのバッファー処理*ストリーム*です。 *ストリーム*引数は、読み取りまたは書き込みがされてがいないを開いているファイルを参照する必要があります。 場合、*バッファー*引数は**NULL**ストリームがされていない ffered ではありません。 場合は、バッファーする必要がありますの長さの文字配列**BUFSIZ**ここで、 **BUFSIZ** STDIO で定義されているバッファーのサイズは、します。H. 所定のストリームに対してシステムによって割り当てられた既定のバッファーではなく、ユーザーが指定したバッファーが I/O バッファー処理に使用されます。 **Stderr**ストリームは既定では、されていない ffered ではありませんが、使用することができます**setbuf**へのバッファーを割り当てる**stderr**です。

**setbuf**代わりました[setvbuf](setvbuf.md)、新しいコード優先のルーチンであります。 **setbuf**既存のコードとの互換性は保持されます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
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

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
