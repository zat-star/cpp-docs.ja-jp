---
title: tmpfile_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- tmpfile_s
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
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d9ac079ce833f65a4a2add57bbc0be93c97902e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="tmpfiles"></a>tmpfile_s
一時ファイルを作成します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [tmpfile](../../c-runtime-library/reference/tmpfile.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pFilePtr`  
 ストリームに生成されたポインターのアドレスを格納するポインターのアドレスです。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`pFilePtr`|**戻り値**|`pFilePtr` **の内容**|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|変更されない|  
  
 上記のパラメーターの検証エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、戻り値は `EINVAL` になります。  
  
## <a name="remarks"></a>コメント  
 `tmpfile_s` 関数は一時ファイルを作成し、`pFilePtr` 引数にそのストリームへのポインターを与えます。 一時ファイルはルート ディレクトリに作成されます。 ルート ディレクトリ以外のディレクトリに一時ファイルを作成するには、[tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) または [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](../../c-runtime-library/reference/fopen-wfopen.md) と共に使用します。  
  
 ファイルを開けない場合、`tmpfile_s` は `NULL` を `pFilePtr` パラメーターに書き込みます。 この一時ファイルは、ファイルが閉じられたとき、プログラムが正常に終了したとき、または `_rmtmp` が呼び出されたときに、自動的に削除されます。これは、現在の作業ディレクトリが変更されていないことを前提とします。 一時ファイルは `w+b` (バイナリ読み書き両用) モードで開かれます。  
  
 `tmpfile_s.` で `TMP_MAX_S` (STDIO.H を参照) よりも多く呼び出しを試行した場合は、エラーが発生することがあります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
> [!NOTE]
>  この例では、Windows Vista を管理者権限で実行する必要があります。  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)