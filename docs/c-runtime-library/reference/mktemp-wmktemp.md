---
title: "_mktemp、_wmktemp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmktemp"
  - "_mktemp"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tmktemp"
  - "wmktemp"
  - "tmktemp"
  - "_wmktemp"
  - "_mktemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktemp 関数"
  - "_tmktemp 関数"
  - "_wmktemp 関数"
  - "ファイル [C++], 一時"
  - "mktemp 関数"
  - "一時ファイル [C++]"
  - "tmktemp 関数"
  - "wmktemp 関数"
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _mktemp、_wmktemp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一意のファイル名を作成します。  これらの関数のセキュリティを強化したバージョンについては、「[\_mktemp\_s、\_wmktemp\_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 `template`  
 ファイル名のパターン。  
  
## 戻り値  
 これらの関数は、変更したテンプレートへのポインターを返します。  `template` が適切形作られればまたはこれ以上の一意の名前が特定のテンプレートから作成できません関数の戻り値 `NULL`。  
  
## 解説  
 `_mktemp` 関数は `template` の引数を変更して、一意のファイル名を作成します。  `_mktemp` 関数は、ランタイム システムで現在使用されているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。  ワイド文字を扱う場合は、`_mktemp` ではなく `_wmktemp` を使用します。`_wmktemp` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  `_wmktemp` 関数と `_mktemp` 関数の動作は、`_wmktemp` 関数がマルチバイト文字列を扱わない点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 `base` が指定した、X は `_mktemp`で指定された文字のプレースホルダーが新しいファイル名の一部である場合、`template` 引数にフォーム `base`XXXXXX が含まれています。  `template` の各プレースホルダー文字には、大文字の X を指定する必要があります。  `_mktemp` は `base` を保持し、後に続く X のうち先頭の X を英字に置き換えます。  `_mktemp` は 5 桁の値に次の残りの;を置き換えます。この値は、プログラムの呼び出しプロセスを識別する一意の数値呼び出し元スレッドです。  
  
 `_mktemp` への呼び出しが成功 `template`を変更します。  同じ `template` 引数を使用して同じプロセスまたはスレッドから呼び出されると、`_mktemp` は、前の呼び出しで `_mktemp` から返された名前と一致するファイル名を調べます。  指定した名前のファイルが存在しない場合、`_mktemp` はその名前を返します。  以前返されたすべての名前のファイルが存在する場合、`_mktemp` は、その名前の英字部分をアルファベット順の次の小文字に置き換えて、新しい名前を作成します。  たとえば、`base` が次のような場合があります。  
  
```  
fn  
```  
  
 と `_mktemp` で指定した 5 桁の値が 12345 の場合、返される名です:次のとおりです。  
  
```  
fna12345  
```  
  
 この名前が FNA12345 ファイルの作成に使用され、そのファイルがまだ存在する場合、`template` に同じ `base` を指定して同じプロセスまたはスレッドを呼び出すと、次の名前が返されます。  
  
```  
fnb12345  
```  
  
 FNA12345 が存在しない場合は、次の名前がもう一度返されます。  
  
```  
fna12345  
```  
  
 `_mktemp` は、base 値と template 値をどのように組み合わせても、最大で 26 個の一意のファイル名を作成できます。  したがって、この例で使用されている `base` 値と `template` 値に対して `_mktemp` が作成できる最後の一意のファイル名は FNZ12345 になります。  
  
 失敗すると、`errno` が設定されます。  `template` に無効な形式 \(数が 6 個の X\) の場合、`errno` は `EINVAL`に設定されます。  26 の有効なファイル名がすべて存在するため `_mktemp` に一意の名前を作成できない場合は、`_mktemp` は空の文字列にテンプレートを設定し、`EEXIST`を返します。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mktemp`|\<io.h\>|  
|`_wmktemp`|\<io.h または\> wchar.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **一意のファイル名は fna03912 です**  
**一意のファイル名は fnb03912 です**  
**一意のファイル名は fnc03912 です**  
**一意のファイル名は fnd03912 です**  
**一意のファイル名は fne03912 です**  
**一意のファイル名は fnf03912 です**  
**一意のファイル名は fng03912 です**  
**一意のファイル名は fnh03912 です**  
**一意のファイル名は fni03912 です**  
**一意のファイル名は fnj03912 です**  
**一意のファイル名は fnk03912 です**  
**一意のファイル名は fnl03912 です**  
**一意のファイル名は fnm03912 です**  
**一意のファイル名は fnn03912 です**  
**一意のファイル名は fno03912 です**  
**一意のファイル名は fnp03912 です**  
**一意のファイル名は fnq03912 です**  
**一意のファイル名は fnr03912 です**  
**一意のファイル名は fns03912 です**  
**一意のファイル名は fnt03912 です**  
**一意のファイル名は fnu03912 です**  
**一意のファイル名は fnv03912 です**  
**一意のファイル名は fnw03912 です**  
**一意のファイル名は fnx03912 です**  
**一意のファイル名は fny03912 です**  
**一意のファイル名は fnz03912 です**  
**テンプレートを作成する問題を示します。**  
**一意のファイル名をクリックします。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../Topic/_getpid.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)