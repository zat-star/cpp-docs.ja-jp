---
title: "_mktemp、_wmktemp | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
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
ms.openlocfilehash: 1e56ba6f238c62a220966701e7b1ced1dd2ec4ea
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="mktemp-wmktemp"></a>_mktemp、_wmktemp
一意のファイル名を作成します。 これらの関数のセキュリティを強化したバージョンについては、「[_mktemp_s、_wmktemp_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `template`  
 ファイル名のパターン。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、変更されたテンプレートへのポインターを返します。 この関数は、`template` の形式が正しくないか、指定したテンプレートから一意の名前をこれ以上作成できない場合、`NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_mktemp` 関数は、`template` 引数を変更することで、一意のファイル名を作成します。 `_mktemp` は、ランタイム システムで現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。 ワイド文字を扱う場合は、`_wmktemp` ではなく `_mktemp` を使用します。`_wmktemp` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 `_wmktemp` がマルチバイト文字列を処理しない点を除き、`_wmktemp` と `_mktemp` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 `template`引数が、フォーム`base` *XXXXXX*ここで、`base`が提供する、新しいファイル名の一部で各 X がで指定された文字のプレース ホルダー`_mktemp`です。 `template` 内の各プレースホルダー文字は大文字の X である必要があります。`_mktemp` では、`base` を保持し、最初の後続の X を英字 1 文字で置換します。 `_mktemp` は、これに続く残りの X を 5 桁の値で置換します。この値は、呼び出し元のプロセスを識別するか、マルチスレッド プログラムの場合に呼び出し元のスレッドを識別する一意の番号です。  
  
 呼び出しが成功した `_mktemp` ごとに、`template` が変更されます。 同じプロセスまたはスレッドによる同じ `template` 引数を使用した後続の呼び出しごとに、`_mktemp` では、以前の呼び出しで `_mktemp` が返した名前と一致するファイル名がないかチェックします。 指定した名前のファイルが存在しない場合、`_mktemp` はその名前を返します。 以前に返したすべての名前のファイルが存在する場合、`_mktemp` は、以前返した名前で使用していた英字 1 文字を、次の使用可能な小文字 1 文字 ('a' から 'z' の順) で置換することで、新しい名前を作成します。 たとえば、`base` が次の値で、  
  
```  
fn  
```  
  
 `_mktemp` によって提供される 5 桁の値が 12345 の場合、返される最初の名前は、次のようになります。  
  
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
  
 `_mktemp` では、ベース値とテンプレート値の任意の組み合わせから最大 26 通りの一意のファイル名を作成できます。 そのため、FNZ12345 は、この例で使用されている `base` と `template` の値に対して `_mktemp` が作成できる最後の一意のファイル名です。  
  
 失敗した場合は、`errno` が設定されます。 `template` の形式が無効な場合 (X が 6 個未満など) は、`errno` が `EINVAL` に設定されます。 候補となる 26 個すべてのファイル名が既に存在していて `_mktemp` が一意の名前を作成できない場合、`_mktemp` はテンプレートを空の文字列に設定し、`EEXIST` を返します。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_mktemp`|\<io.h>|  
|`_wmktemp`|\<io.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
```Output  
Unique filename is fna03912  
Unique filename is fnb03912  
Unique filename is fnc03912  
Unique filename is fnd03912  
Unique filename is fne03912  
Unique filename is fnf03912  
Unique filename is fng03912  
Unique filename is fnh03912  
Unique filename is fni03912  
Unique filename is fnj03912  
Unique filename is fnk03912  
Unique filename is fnl03912  
Unique filename is fnm03912  
Unique filename is fnn03912  
Unique filename is fno03912  
Unique filename is fnp03912  
Unique filename is fnq03912  
Unique filename is fnr03912  
Unique filename is fns03912  
Unique filename is fnt03912  
Unique filename is fnu03912  
Unique filename is fnv03912  
Unique filename is fnw03912  
Unique filename is fnx03912  
Unique filename is fny03912  
Unique filename is fnz03912  
Problem creating the template.  
Out of unique filenames.  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam、_wtempnam、tmpnam、_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)
