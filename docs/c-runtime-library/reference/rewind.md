---
title: rewind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rewind
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
f1_keywords: rewind
dev_langs: C++
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78cb2d761e7625dac7073927b7b7f1a06fcf1759
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rewind"></a>rewind
ファイル ポインターをファイルの先頭に位置変更します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 **FILE** 構造体へのポインター。  
  
## <a name="remarks"></a>コメント  
 **rewind** 関数は、`stream` に関連付けられているファイル ポインターをファイルの先頭に位置変更します。 **rewind** 関数の呼び出しは、次の関数の呼び出しと似ています。  
  
 **(void) fseek(** `stream`**, 0L,** `SEEK_SET` **);**  
  
 ただし、`fseek` 関数とは異なり、**rewind** 関数はストリームのエラー インジケーターと EOF (EOF: end-of-file) インジケーターをクリアします。 また、`fseek` 関数はポインターが正常に移動したかどうかを示す値を返しますが、**rewind** 関数は返しません。  
  
 キーボード バッファをクリアするには、既定でキーボードに関連付けられている標準入力ストリーム (`stdin`) を引数に指定して **rewind** 関数を使用します。  
  
 ストリームが `NULL` ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を返し、`EINVAL` に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|**rewind**|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## <a name="output"></a>出力  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)