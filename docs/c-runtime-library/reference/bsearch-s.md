---
title: "bsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch_s"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "bsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [CRT]、バイナリ検索"
  - "bsearch_s 関数"
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# bsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並べ替えられた配列のバイナリ検索を実行します。 これは「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[bsearch](../../c-runtime-library/reference/bsearch.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
);  
```  
  
#### パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索データのベースへのポインター。  
  
 `num`  
 要素の数。  
  
 `width`  
 要素の幅。  
  
 `compare`  
 2 つの要素を比較するコールバック関数。 最初の引数は、`context` ポインターです。 2 番目の引数は、検索用の `key` へのポインターです。 3 番目の引数は、`key` と比較する配列要素へのポインターです。  
  
 `context`  
 比較関数内でアクセスできるオブジェクトへのポインター。  
  
## 戻り値  
 `bsearch_s` は、`base` が指し示す配列内の `key` の発生個所へのポインターを返します。`key` がない場合、関数は `NULL` を返します。 配列が昇順でないか、同一キーで重複するレコードがある場合、結果は予測不可能になります。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数が `NULL` を返します。 詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
### エラー条件  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|\!\= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|\= 0|`EINVAL`|  
|任意|任意|`NULL`|1 つ|任意|`EINVAL`|  
  
## 解説  
 `bsearch_s` 関数は `num` 要素の並べ替えられた配列のバイナリ検索を、`width` バイト数の単位で実行します。`base` 値は、検索対象の配列のベースへのポインターであり、`key` は検索されている値です。`compare` パラメーターはユーザーが指定したルーチンへのポインターであり、要求されたキーを配列要素と比較し、その関係を示す次のいずれかの値を返します。  
  
|`compare` ルーチンによって返される値|説明|  
|-----------------------------|--------|  
|\< 0|キーは配列要素より小さい。|  
|0|キーは配列要素と等しい。|  
|\> 0|キーは配列要素より大きい。|  
  
 `context` ポインターは、検索対象のデータ構造体がオブジェクトの一部であり、関数をオブジェクトのアクセス メンバーと比較する場合に役立ちます。`compare` 関数は void ポインターを該当するオブジェクト型とそのオブジェクトのアクセス メンバーにキャストします。`context` パラメーターを追加すると、`compare` 関数でデータを使用可能にする静的関数を使用する場合の再入バグを回避するために、追加のコンテキストを使用できるので、`bsearch_s` がより安全になります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`bsearch_s`|\<stdlib.h\> および \<search.h\>|  
  
 互換性の詳細については、ランタイム ライブラリ リファレンスの「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 このプログラムでは、[qsort\_s](../../c-runtime-library/reference/qsort-s.md) で文字列の配列を並べ替え、bsearch\_s を使用して "cat" という単語を検索します。  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
cat cow dog goat horse human pig rat cat が 002F0F04 で検出されます  
```  
  
## 同等の .NET Framework 関数  
 <xref:System.Collections.ArrayList.BinarySearch%2A>  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)