---
title: "fread | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fread
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
- fread
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 17
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
ms.openlocfilehash: 1075fc8aad54dfdcada7fe2f4dd8e99706de7d99
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fread"></a>fread
ストリームからデータを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 データの格納場所。  
  
 `size`  
 項目サイズ (バイト単位)。  
  
 `count`  
 読み取る項目の最大数。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `fread`返します。 実際に読み取られた完全な項目の数、可能性のあるより小さい`count`エラーが発生した場合、またはファイルの末尾が到達する前に発生した場合`count`です。 `feof` 関数または `ferror` 関数を使用すれば、読み取りエラーとファイルの終端に達した状態とを区別できます。 `size`または `count` が 0 である場合、`fread` は 0 を返し、バッファーの内容は変更されません。 `stream` または `buffer` が null ポインターの場合、`fread` は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `fread` 関数は、入力 `stream` から、`size` バイトの `count` 項目まで読み取り、`buffer` に格納します。 `stream` に関連付けられたファイル ポインター (存在する場合) は、実際に読み取られたバイト数でインクリメントされます。 指定したストリームがテキスト モードで開かれている場合は、キャリッジ リターンとライン フィードのペアが 1 つの改行文字に置き換えられます。 この置き換えは、ファイル ポインターまたは戻り値には影響しません。 エラーが発生した場合、ファイル ポインターの位置は不確定になります。 部分的に読み取られた項目の値を特定できません。  
  
 この関数は他のスレッドをロックします。 ロックしないバージョンが必要な場合は、`_fread_nolock` を使用してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fread`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
```Output  
Wrote 25 items  
Number of items read = 25  
Contents of buffer = zyxwvutsrqponmlkjihgfedcb  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)
