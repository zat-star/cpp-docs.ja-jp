---
title: "_mktemp_s、_wmktemp_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mktemp_s
- _wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1289db9b04b9636680439980046fc9532181bd13
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mktemps-wmktemps"></a>_mktemp_s、_wmktemp_s
一意のファイル名を作成します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_mktemp、_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `template`  
 ファイル名のパターン。  
  
 `sizeInChars`  
 `_wmktemp_s` の場合は 1 バイト文字単位、`_mktemp_s` の場合はワイド文字単位のバッファー サイズ。null 終端文字を含みます。  
  
## <a name="return-value"></a>戻り値  
 これらの関数のどちらも、成功した場合は 0 を返し、エラーの場合はエラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`template`|`sizeInChars`|**戻り値**|**テンプレートの新しい値**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|任意|`EINVAL`|`NULL`|  
|正しくない形式 (正しい形式については、「`Remarks`」セクションを参照してください)|任意|`EINVAL`|空の文字列|  
|任意|X の数以下|`EINVAL`|空の文字列|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `EINVAL` が返されます。  
  
## <a name="remarks"></a>コメント  
 `_mktemp_s` 関数は `template` 引数を変更して一意のファイル名を作成します。したがって、呼び出し後、`template` ポインターは新しいファイル名を含む文字列を指します。 `_mktemp_s` は、ランタイム システムによって現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。 `_wmktemp_s` は `_mktemp_s` のワイド文字バージョンです。`_wmktemp_s` の引数はワイド文字列です。 `_wmktemp_s` がマルチバイト文字列を処理しない点を除き、`_wmktemp_s` と `_mktemp_s` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 `template` 引数の形式は `baseXXXXXX` です。ここで `base` は新しいファイル名の一部として指定される内容であり、各 X は `_mktemp_s` によって指定される文字のプレースホルダーです。 `template` 内の各プレースホルダー文字は大文字の X である必要があります。`_mktemp_s` では、`base` を保持し、最初の後続の X を英字 1 文字で置換します。 `_mktemp_s` は、これに続く残りの X を 5 桁の値で置換します。この値は、呼び出し元のプロセスを識別するか、マルチスレッド プログラムの場合に呼び出し元のスレッドを識別する一意の番号です。  
  
 呼び出しが成功した `_mktemp_s` ごとに、`template` が変更されます。 同じプロセスまたはスレッドによる同じ `template` 引数を使用した後続の呼び出しごとに、`_mktemp_s` では、以前の呼び出しで `_mktemp_s` が返した名前と一致するファイル名がないかチェックします。 指定した名前のファイルが存在しない場合、`_mktemp_s` はその名前を返します。 以前に返したすべての名前のファイルが存在する場合、`_mktemp_s` は、以前返した名前で使用していた英字 1 文字を、次の使用可能な小文字 1 文字 ('a' から 'z' の順) で置換することで、新しい名前を作成します。 たとえば、`base` が次の値で、  
  
```  
fn  
```  
  
 `_mktemp_s` によって提供される 5 桁の値が 12345 の場合、返される最初の名前は、次のようになります。  
  
```  
fna12345  
```  
  
 この名前を使用してファイル FNA12345 が作成され、このファイルがまだ使用されている場合、`template` に同じ `base` を使用する同じプロセスまたはスレッドからの呼び出しで返される次の名前は、次のようになります。  
  
```  
fnb12345  
```  
  
 FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。  
  
```  
fna12345  
```  
  
 `_mktemp_s` では、ベース値とテンプレート値の任意の組み合わせから最大 26 通りの一意のファイル名を作成できます。 そのため、FNZ12345 は、この例で使用されている `base` と `template` の値に対して `_mktemp_s` が作成できる最後の一意のファイル名です。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h>|  
|`_wmktemp_s`|\<io.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)