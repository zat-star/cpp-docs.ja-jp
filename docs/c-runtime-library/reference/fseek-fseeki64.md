---
title: "fseek、_fseeki64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
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
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek、_fseeki64
指定した場所にファイル ポインターを移動します。  
  
## <a name="syntax"></a>構文  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `offset`  
 `origin` から読み取られたバイト数。  
  
 `origin`  
 最初の位置。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`fseek` および `_fseeki64` は 0 を返します。 それ以外の場合は、0 以外の値を返します。 シーク非対応のデバイスでは、戻り値は未定義です。 `stream` が null ポインターであるか、`origin` が下に説明されているいずれかの許可された値ではない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、`fseek` および `_fseeki64` は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。  
  
## <a name="remarks"></a>コメント  
 `fseek`と`_fseeki64`関数ファイル ポインター (存在する場合) に関連付けられている移動`stream`されている新しい場所に`offset`からバイト`origin`です。 ストリームの次の操作は、新しい場所で行われます。 更新用に開かれているストリームでの次の操作は読み取りまたは書き込みのいずれかです。 元の引数は、STDIO.H で定義されている、次の定数のいずれかである必要があります。  
  
 `SEEK_CUR`  
 ファイル ポインターの現在の位置。  
  
 `SEEK_END`  
 EOF (ファイル終端)。  
  
 `SEEK_SET`  
 ファイルの先頭。  
  
 `fseek` と `_fseeki64` を使用して、ファイル内の任意の場所にポインターを移動できます。 ポインターは、ファイルの末尾を越えて配置することもできます。 `fseek`および`_fseeki64`ファイルの終端のインジケーターをクリアし、前の効果が無視`ungetc`に対して呼び出す`stream`です。  
  
 データを追加するためにファイルを開く場合、現在のファイルの位置は、次の書き込みが発生する場所ではなく最後の I/O 操作によって決まります。 追加のために開かれたファイルで I/O 操作がまだ発生していない場合、ファイルの位置はファイルの先頭です。  
  
 テキスト モードで開いたストリーム`fseek`と`_fseeki64`キャリッジ リターンとライン フィード翻訳可能性があるため、用途が限定`fseek`と`_fseeki64`予期しない結果を生成します。 唯一`fseek`と`_fseeki64`操作がテキスト モードで開いたストリームで動作する保証は。  
  
-   元の値のいずれかに対して相対的なオフセット 0 でシークします。  
  
-   呼び出しから返されたオフセット値を持つファイルの先頭からのシーク`ftell`を使用する場合`fseek`または`_ftelli64`を使用する場合`_fseeki64`です。  
  
 テキスト モードでも、Ctrl + Z は入力時に EOF (EOF: end-of-file) 文字として解釈されます。 読み取りおよび書き込みの両方のために開かれたファイルでは、`fopen` および関連するすべてのルーチンが、ファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、`fseek` と `ftell` または `_fseeki64` と `_ftelli64` の組み合わせを使用して、CTRL+Z で終わるファイルの中身を移動するとき、ファイル末尾付近で `fseek` または `_fseeki64` が正しく動作しないことがあるためです。  
  
 バイト オーダー マーク (BOM) で始まるファイルを CRT で開くときには、ファイル ポインターは BOM の後ろ (つまり、ファイルの実際のコンテンツの開始位置) に配置されます。 `fseek` をファイルの先頭に置く必要がある場合は、`ftell` を使用して初期位置を取得し、0 の位置ではなくそこに `fseek` を配置します。  
  
 この関数では、実行中に他のスレッドをロックするので、スレッド セーフです。 ロックしないバージョンについては、「[_fseek_nolock、_fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell、_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek、_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
