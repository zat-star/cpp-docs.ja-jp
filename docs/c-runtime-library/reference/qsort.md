---
title: "qsort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "qsort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "qsort 関数"
  - "クイックソート アルゴリズム"
  - "配列の並べ替え"
  - "配列 [CRT]、並べ替え"
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# qsort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

簡単な並べ替えを実行します。  この関数のセキュリティが強化されたバージョンについては、「[qsort\_s](../../c-runtime-library/reference/qsort-s.md)」を参照してください。  
  
## 構文  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### パラメーター  
 `base`  
 ターゲット配列の開始。  
  
 `num`  
 要素の配列のサイズ。  
  
 `width`  
 バイトの要素のサイズ。  
  
 `compare`  
 2 種類の配列要素を比較し、関係を指定する値を返すユーザーが指定したルーチンへのポインター。  
  
## 解説  
 `qsort` 関数は `num` 要素の配列を、`width` の各バイト並べ替えるになく並べ替えアルゴリズムを実装します。  引数 `base` は並べ替えられるよう配列のベースへのポインターです。  `qsort` は 並べ替えられた要素を使用すると、この配列を上書きします。  
  
 `qsort` は 一つ以上の並べ替え時間中に `compare` ルーチンを呼び出して各呼び出しの 2 種類の配列要素へのポインターを渡します。  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 ルーチンは、次の値の要素は 1 とを比較します。  
  
|関数の戻り値を比較します。|説明|  
|-------------------|--------|  
|\< 0|`elem1` が `elem2` より小さい|  
|0|`elem2`への`elem1` の等価|  
|\> 0|`elem1` が `elem2` より大きい|  
  
 配列は、比較関数によって定義されている、昇順に並べ替えられます。  かからない順序で配列を並べ替えるには、「より大きい」と比較関数の「以下の感覚をより」に戻します。  
  
 この関数は、パラメーターを検証します。  `compare` または `num` が `NULL`であるか、または `base` が `NULL` になり`num` \*は 0 以外のか、`width` が小さい場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `EINVAL`への関数の戻り値と `errno` が設定されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`qsort`|\<stdlib.h と\> search.h \<\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
  **男の子は、任意の優先が必要です。**   
## 同等の .NET Framework 関数  
 [System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)