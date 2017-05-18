---
title: _read | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
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
ms.openlocfilehash: 6387edb05977f90fe9fb2419a1eccb47ac0b7b43
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

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
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 *バッファー*  
 データの格納場所。  
  
 *count*  
 最大バイト数。  
  
## <a name="return-value"></a>戻り値  
 _**読み取り**小さい場合があります、読み取られたバイト数を返しますより*カウント*よりも少ない場合*カウント*ファイル内の残りのバイト数または各キャリッジ リターンとラインが (CR-LF) のペアをフィードする場合は、1 つの改行文字に置き換えられます、ファイルがテキスト モードで開かれた場合。 戻り値ではその単一の改行文字だけがカウントされます。 この置き換えは、ファイル ポインターには影響しません。  
  
 この関数はファイルの終わりで読み取りをすると、0 を返します。 `fd` が無効であるか、ファイルが読み取り用に開かれていないか、ファイルがロックされているかの場合、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、 `errno` を `EBADF`に設定します。  
  
 *バッファー*が **NULL** の場合は、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、 `errno` は `EINVAL` に設定されます。  
  
 このリターン コードとその他のリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_read` 関数は *count* の最大バイトを、`fd` に関連付けられているファイルから*バッファー*に読み込みます。 読み取り操作は、指定されたファイルに関連付けられたファイル ポインターの現在の位置で開始されます。 読み取り操作後、ファイル ポインターは、次の未読の文字を指します。  
  
 ファイルがテキスト モードで開かれた場合、ファイルの終わりを示すインジケーターとして扱われる CTRL + Z の文字が `_read` で検出された時点で、読み取りは終了します。 ファイルの終わりのインジケーターをクリアするには、[_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) を使用します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
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
  
## <a name="input-crtreadtxt"></a>入力: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## <a name="output"></a>出力  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>関連項目  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_write](../../c-runtime-library/reference/write.md)
