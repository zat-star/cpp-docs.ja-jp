---
title: "bsearch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch"
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
  - "bsearch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [CRT]、バイナリ検索"
  - "bsearch 関数"
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# bsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

並べ替えられた配列のバイナリ検索を実行します。 この関数のセキュリティが強化されたバージョンについては、「[bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)」を参照してください。  
  
## 構文  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
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
 2 つの要素を比較するコールバック関数。 最初のものは検索対象のキーへのポインターで、2 番目はキーと比較する配列要素へのポインターです。  
  
## 戻り値  
 `bsearch` は、`base`.が指し示す配列内の `key` の発生個所へのポインターを返します。`key` がない場合、関数は `NULL` を返します。 配列が昇順でないか、同一キーで重複するレコードがある場合、結果は予測不可能になります。  
  
## 解説  
 `bsearch` 関数は `num` 要素の並べ替えられた配列のバイナリ検索を、`width` バイト数の単位で実行します。`base` 値は、検索対象の配列のベースへのポインターであり、`key` は検索されている値です。`compare` パラメーターはユーザーが指定したルーチンへのポインターであり、要求されたキーを配列要素と比較し、その関係を示す次のいずれかの値を返します。  
  
|`compare` ルーチンによって返される値|説明|  
|-----------------------------|--------|  
|\< 0|キーは配列要素より小さい。|  
|0|キーは配列要素と等しい。|  
|\> 0|キーは配列要素より大きい。|  
  
 この関数は、パラメーターを検証します。`compare`、`key`、または `num` が `NULL` の場合、`base` が `NULL` であり \*`num` が 0 以外の場合、あるいは `width` が 0 の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`bsearch`|\<stdlib.h\> および \<search.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 このプログラムでは、qsort で文字列の配列を並べ替え、bsearch を使用して "cat" という単語を検索します。  
  
```  
// crt_bsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( char **arg1, char **arg2 )  
{  
   /* Compare all of both strings: */  
   return _strcmpi( *arg1, *arg2 );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
   char **result;  
   char *key = "cat";  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const   
   void*, const void*))compare );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),  
                              sizeof( char * ), (int (*)(const void*, const void*))compare );  
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
 [System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)