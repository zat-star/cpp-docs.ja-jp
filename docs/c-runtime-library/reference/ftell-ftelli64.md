---
title: "ftell、_ftelli64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 220b34e5bba7a4a6716d6ef18d6621b58d36ecc3
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="ftell-ftelli64"></a>ftell、_ftelli64
ファイル ポインターの現在の位置を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 ターゲット `FILE` 構造体。  
  
## <a name="return-value"></a>戻り値  
 `ftell` および `_ftelli64` は、ファイルの現在の位置を返します。 によって返される値`ftell`と`_ftelli64`キャリッジ リターンとライン フィードの変換のため、テキスト モードで開いたストリームの物理バイト オフセットを表さない場合があります。 使用して`ftell`で`fseek`または`_ftelli64`で`_fseeki64`正しくファイルの場所に戻ります。 エラーが発生した`ftell`と`_ftelli64`」の説明に従って、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の続行には、これらの関数の戻り値-1 L セットが許可された場合`errno`ERRNO で定義されている 2 つの定数のいずれかにします。H. `EBADF` 定数は、`stream` 引数が有効なファイル ポインター値ではないかまたは開くファイルを参照していないことを意味します。 `EINVAL` は、無効な `stream` 引数が関数に渡されたことを意味します。 (ターミナルやポインターなどの) シーク非対応のデバイスの場合、または `stream` が開くファイルを参照していない場合、戻り値は未定義です。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `ftell`と`_ftelli64`関数に関連付けられたファイル ポインター (存在する場合) の現在の位置を取得する`stream`です。 位置は、ストリームの先頭を基準としたオフセットとして表されます。  
  
 データを追加するためにファイルを開く場合、現在のファイルの位置は、次の書き込みが発生する場所ではなく最後の I/O 操作によって決まります。 たとえば、追加のためにファイルが開かれ、最後の操作が読み取りだった場合、ファイルの位置は、次の書き込みが開始される位置ではなく、次の読み取り操作が開始される位置になります  (追加のためにファイルが開かれるときには、ファイルの位置は書き込み操作が開始される前にファイルの末尾に移動されます)。追加のために開かれたファイルで I/O 操作がまだ発生していない場合、ファイルの位置はファイルの先頭です。  
  
 テキスト モードでは、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りおよび書き込みの両方のために開かれたファイルでは、`fopen` および関連するすべてのルーチンが、ファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、`ftell` と `fseek` または `_ftelli64` と `_fseeki64` の組み合わせを使用して、CTRL+Z で終わるファイルの中身を移動するとき、ファイル末尾付近で `ftell` または `_ftelli64` が正しく動作しないことがあるためです。  
  
 この関数は実行中に呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「`_ftell_nolock`」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|省略可能なヘッダー|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h>|\<errno.h>|  
|`_ftelli64`|\<stdio.h>|\<errno.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek、_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)
