---
title: _lfind_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind_s
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
- lfind_s
- _lfind_s
dev_langs: C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bff33c66ebe8bdb2b5eb497aad2e3a11bc04a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lfinds"></a>_lfind_s
指定されたキーの線形探索を実行します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_lfind](../../c-runtime-library/reference/lfind.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索データのベースへのポインター。  
  
 `num`  
 配列要素の数。  
  
 `size`  
 バイト単位での配列要素のサイズ。  
  
 `compare`  
 比較ルーチンへのポインター。 最初のパラメーターは `context` ポインターです。 2 番目のパラメーターは、検索用のキーへのポインターです。 3 番目のパラメーターは、キーと比較する配列要素へのポインターです。  
  
 `context`  
 比較関数内でアクセスされることのあるオブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 キーが見つかった場合、`_lfind_s` は `key` と一致する `base` の配列要素のポインターを返します。 キーが見つからない場合、`_lfind_s` は `NULL` を返します。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  
  
### <a name="error-conditions"></a>エラー条件  
  
|key|base|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|!= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|ゼロ|`EINVAL`|  
|任意|任意|`NULL`|1 つ|任意|`EINVAL`|  
  
## <a name="remarks"></a>コメント  
 `_lfind_s` 関数は、`num` 要素の配列の値 `key` に対する一方向の検索を、`width` バイトごとに実行します。 `bsearch_s` とは異なり、`_lfind_s` では配列を並べ替える必要がありません。 `base` 引数は、検索する配列のベースへのポインターです。 `compare` 引数は、2 つの配列要素を比較して、それらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。 `_lfind_s` は検索中に `compare` ルーチンを 1 回以上呼び出し、各呼び出しにおいて `context` ポインターと 2 つの配列要素へのポインターを渡します。 `compare` ルーチンは要素を比較し、ゼロ以外 (要素が異なる場合) または 0 (要素が同じ場合) を返す必要があります。  
  
 `_lfind_s` は `_lfind` と似ていますが、比較関数の引数と関数のパラメーター リストへ `context` ポインターが追加されている点が異なります。 `context` ポインターは、検索対象のデータ構造体がオブジェクトの一部であり、`compare` 関数でオブジェクトのメンバーにアクセスする必要がある場合に役立ちます。 `compare` 関数は void ポインターを該当するオブジェクト型にキャストして、そのオブジェクトのメンバーにアクセスできます。 `context` パラメーターを追加すると、`compare` 関数でデータを使用可能にする静的変数を使用する場合の再入バグを回避するために、追加のコンテキストを使用できるので、`_lfind_s` がより安全になります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_lfind_s`|\<search.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
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
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)