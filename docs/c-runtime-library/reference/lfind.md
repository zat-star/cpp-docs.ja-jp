---
title: _lfind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lfind
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind
- _lfind
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4101348ee1344accb0a0117c997dceb1c79d0b40
ms.lasthandoff: 02/24/2017

---
# <a name="lfind"></a>_lfind
指定されたキーの線形探索を実行します。 この関数のセキュリティが強化されたバージョンについては、「[_lfind_s](../../c-runtime-library/reference/lfind-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索データのベースへのポインター。  
  
 `num`  
 配列要素の数。  
  
 `width`  
 配列要素の幅。  
  
 `compare`  
 比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目の引数は、キーと比較する配列要素へのポインターです。  
  
## <a name="return-value"></a>戻り値  
 キーが見つかった場合、`_lfind` は `key` と一致する `base` の配列要素のポインターを返します。 キーが見つからない場合、`_lfind` は `NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_lfind` 関数は、`num` 要素の配列の値 `key` に対する一方向の検索を、`width` バイトごとに実行します。 `bsearch` とは異なり、`_lfind` では配列を並べ替える必要がありません。 `base` 引数は、検索する配列のベースへのポインターです。 `compare` 引数は、2 つの配列要素を比較して、それらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。 `_lfind` は検索中に `compare` ルーチンを&1; 回以上呼び出し、各呼び出しにおいて&2; つの配列要素へのポインターを渡します。 `compare` ルーチンは要素を比較し、ゼロ以外 (要素が異なる場合) または 0 (要素が同じ場合) を返す必要があります。  
  
 この関数は、パラメーターを検証します。 `compare`、`key` または `num` が `NULL` である場合、`base` が NULL で *`num` がゼロ以外の場合、または `width` がゼロより小さい場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `NULL`が返されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_lfind`|\<search.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
Hello found  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## <a name="see-also"></a>関連項目  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)
