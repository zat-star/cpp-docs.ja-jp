---
title: qsort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: qsort
dev_langs: C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e3f6d964f4cf4debefa3044a458704554233447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="qsort"></a>qsort
クイック ソートを実行します。 この関数のセキュリティが強化されたバージョンについては、「[qsort_s](../../c-runtime-library/reference/qsort-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `base`  
 対象となる配列の先頭。  
  
 `num`  
 配列サイズ (要素数)。  
  
 `width`  
 要素のサイズ (バイト単位)。  
  
 `compare`  
 2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。  
  
## <a name="remarks"></a>コメント  
 `qsort` 関数は、それぞれが `width` バイトの `num` 要素から成る配列を並べ替えるためのクイック ソート アルゴリズムを実装します。 引数 `base` は、並べ替える配列のベースへのポインターです。 `qsort` は、並べ替えた要素を使用して、この配列を上書きします。  
  
 `qsort` は並べ替え中に `compare` ルーチンを 1 回または複数回呼び出し、各呼び出しにおいて 2 つの配列要素へのポインターを渡します。  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 ルーチンは、要素を比較し、次の値のいずれかを返します。  
  
|関数の戻り値の比較|説明|  
|-----------------------------------|-----------------|  
|< 0|`elem1` が `elem2` より小さい|  
|0|`elem1` が `elem2` と等しい|  
|> 0|`elem1` が `elem2` より大きい|  
  
 配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。  
  
 この関数は、パラメーターを検証します。 `compare` または `num` が `NULL` である場合、または `base` が `NULL` で *`num` がゼロ以外の場合、または `width` がゼロ未満の場合、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可されると、この関数は `errno` を返し、`EINVAL` に設定します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h> および \<search.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
boy deserves every favor good  
```  
  
## <a name="see-also"></a>参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)