---
title: "_lfind | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind"
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
  - "lfind"
  - "_lfind"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lfind 関数"
  - "配列 [CRT], 検索"
  - "検索 (配列の中でのキーの)"
  - "lfind 関数"
  - "リニア サーチ"
  - "検索, リニア"
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lfind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したキーのリニア サーチを実行します。  この関数のセキュリティが強化されたバージョンについては、「[\_lfind\_s](../Topic/_lfind_s.md)」を参照してください。  
  
## 構文  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索するデータ配列のベースへのポインター。  
  
 `num`  
 配列の要素数。  
  
 `width`  
 配列要素の幅。  
  
 `compare`  
 比較ルーチンへのポインター。  最初のパラメーターは、検索用に調整するポインターです。  2 番目のパラメーターは、キーと比較される配列要素へのポインターです。  
  
## 戻り値  
 キーがある場合は、`_lfind``base` で配列要素へのポインターを返します。`key`一致  キーが存在しない場合、`_lfind` は `NULL`を返します。  
  
## 解説  
 `_lfind` 関数は `num` 要素の配列、`width` の各バイトの値 `key` のリニア サーチを実行します。  `bsearch`とは異なり、`_lfind` は配列が並べ替えられるように必要がありません。  `base` の引数は、検索する配列のベースへのポインターです。  `compare` の引数は、2 種類の配列要素を比較し、指定されている値を返す関係ユーザーが指定したルーチンへのポインターです。  `_lfind` は 一つ以上の時間各呼び出しの 2 種類の配列要素へのポインターを渡す検索中に `compare` ルーチンを呼び出します。  `compare` ルーチンは、要素を比較し、0 以外の \(要素を意味して異なるしてください\) 0 を返す必要があります \(要素を意味して同じにしてください。  
  
 この関数は、パラメーターを検証します。  `compare`、`key` または `num` が `NULL`であるか、または `base` が null になり`num` \*は 0 以外のか、`width` が小さい場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_lfind`|\<search.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
  **Hello が見つからない**   
## 同等の .NET Framework 関数  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind\_s](../Topic/_lfind_s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)