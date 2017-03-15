---
title: _lsearch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch
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
- _lsearch
- lsearch
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
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
ms.openlocfilehash: 05248645487edfc46b8adc5754bf99e46ee6911f
ms.lasthandoff: 02/24/2017

---
# <a name="lsearch"></a>_lsearch
ある値に関して一方向に検索を実行し、見つからない場合はリストの末尾に追加します。 この関数のセキュリティが強化されたバージョンについては、「[_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索する配列のベースへのポインター。  
  
 `num`  
 要素の数。  
  
 `width`  
 配列の各要素の幅。  
  
 `compare`  
 比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。  
  
## <a name="return-value"></a>戻り値  
 キーが見つかった場合、`_lsearch` は `key` と一致する `base` の配列要素のポインターを返します。 キーが見つからない場合は、`_lsearch` は新しく追加された項目へのポインターを配列の末尾に返します。  
  
## <a name="remarks"></a>コメント  
 `_lsearch` 関数は、`num` 要素の配列の値 `key` に対する一方向の検索を、`width` バイトごとに実行します。 `bsearch` とは異なり、`_lsearch` では配列を並べ替える必要がありません。 `key` が見つからない場合、`_lsearch` によって配列の末尾に追加され `num` が増やされます。  
  
 `compare` 引数は、2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。 `_lsearch` は検索中に `compare` ルーチンを&1; 回以上呼び出し、各呼び出しにおいて&2; つの配列要素へのポインターを渡します。 `compare` は要素を比較し、ゼロ以外 (要素が異なる場合) または 0 (要素が同じ場合) を返す必要があります。  
  
 この関数は、パラメーターを検証します。 `compare`、`key` または `num` が `NULL` である場合、`base` が NULL で *`num` がゼロ以外の場合、または `width` がゼロより小さい場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `NULL`が返されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_lsearch`|\<search.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)
