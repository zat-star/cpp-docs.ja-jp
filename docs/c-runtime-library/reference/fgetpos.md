---
title: fgetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
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
ms.openlocfilehash: c53e5742a518934ad0afcfaa06ad4e5905c484e3
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="fgetpos"></a>fgetpos
ストリームのファイル位置インジケーターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 対象のストリーム。  
  
 `pos`  
 位置インジケーターのストレージ。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`fgetpos` は 0 を返します。 失敗した場合は 0 以外の値を返し、`errno` をマニフェスト定数 (STDIO.H に定義されています) のいずれかに設定します。マニフェスト定数の `EBADF` は、指定したストリームが有効なファイル ポインターではないかアクセスできないことを示します。`EINVAL` は、`stream` 値または `pos` の値が無効であることを示します (いずれかが Null ポインターの場合など)。 また、`stream` または `pos` が `NULL` ポインターの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。  
  
## <a name="remarks"></a>コメント  
 `fgetpos` 関数は、`stream` 引数のファイル位置インジケーターの現在の値を取得し、`pos` で示されるオブジェクトに格納します。 `fsetpos` 関数は、`pos` に格納されている情報を後で使用して、`fgetpos` が呼び出された時点の位置まで `stream` 引数のポインターをリセットします。 `pos` 値は内部形式で格納されます。`fgetpos` と `fsetpos` でのみ使用される値です。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetpostxt"></a>入力: crt_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### <a name="output-crtfgetpostxt"></a>出力: crt_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)
