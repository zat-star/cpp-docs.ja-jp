---
title: qsort_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: qsort_s
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
f1_keywords: qsort_s
dev_langs: C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 333473d0b0b7e50e2b0faebef02835dcaf577440
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="qsorts"></a>qsort_s
クイック ソートを実行します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [qsort](../../c-runtime-library/reference/qsort.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
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
 比較関数。 最初の引数は、 `context` ポインターです。 2 番目の引数は、検索用の `key` へのポインターです。 3 番目の引数は、 `key`と比較する配列要素へのポインターです。  
  
 `context`  
 コンテキストへのポインター。コンテキストは、`compare` ルーチンがアクセスする必要があるどのオブジェクトでもかまいません。  
  
## <a name="remarks"></a>コメント  
 `qsort_s` 関数は、それぞれが `width` バイトの `num` 要素から成る配列を並べ替えるためのクイック ソート アルゴリズムを実装します。 引数 `base` は、並べ替える配列のベースへのポインターです。 `qsort_s` は、並べ替えた要素で、この配列を上書きします。 引数 `compare` は、2 つの配列要素を比較して両者の関係を指定する値を返すユーザー指定のルーチンへのポインターです。 `qsort_s` は並べ替え中に `compare` ルーチンを 1 回以上呼び出し、各呼び出しにおいて 2 つの配列要素へのポインターを渡します。  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 ルーチンは、要素を比較し、次の値のいずれかを返す必要があります。  
  
|戻り値|説明|  
|------------------|-----------------|  
|< 0|`elem1` が `elem2` より小さい|  
|0|`elem1` が `elem2` と等しい|  
|> 0|`elem1` が `elem2` より大きい|  
  
 配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可されると、この関数は戻って、`errno` を `EINVAL` に設定します。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|key|base|compare|num|幅|errno|  
|---------|----------|-------------|---------|-----------|-----------|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|!= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|<= 0|`EINVAL`|  
|任意|任意|`NULL`|任意|任意|`EINVAL`|  
  
 `qsort_s` の動作は、`context` パラメーターを持ち `errno` を設定すること以外は `qsort` と同じです。 `context` パラメーターを渡すと、比較関数はオブジェクト ポインターを使用して、オブジェクト機能や、要素ポインターではアクセスできない他の情報にアクセスできます。 追加、`context`パラメーターにより、`qsort_s`ためにのより安全な`context`共有情報を使用できるようにする静的変数を使用して導入された再入バグを避けるために使用できる、`compare`関数。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`qsort_s`|\<stdlib.h > と \<search.h >|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
 次の例で使用する方法、`context`内のパラメーター、`qsort_s`関数。 `context` パラメーターにより、スレッドセーフの並べ替えをより簡単に実行できるようになります。 スレッド セーフを確保するには同期を取らなければならない静的変数を使用するのではなく、並べ替えごとに異なる `context` パラメーターを渡します。 この例では、`context` パラメーターとしてロケール オブジェクトが使用されています。  
  
```  
// crt_qsort_s.cpp  
// compile with: /EHsc /MT  
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4  
// is the n tilde.  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
#define SPANISH_LOCALE "Spanish_Spain.850"  
#define ENGLISH_LOCALE "English_US.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S and \x001f for the n tilde.  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
#define SPANISH_LOCALE "Spanish_Spain.1252"  
#define ENGLISH_LOCALE "English_US.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making sort_array vulnerable to thread  
// conflicts.  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char s1[256];  
    char s2[256];  
    strcpy_s(s1, 256, *(char**)str1);  
    strcpy_s(s2, 256, *(char**)str2);  
    _strlwr_s( s1, sizeof(s1) );  
    _strlwr_s( s2, sizeof(s2) );  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(s1,   
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);  
  
}  
  
void sort_array(char *array[], int num, locale &loc)  
{  
    qsort_s(array, num, sizeof(char*), compare, &loc);  
}  
  
void print_array(char *a[], int c)  
{  
   for (int i = 0; i < c; i++)  
     printf("%s ", a[i]);  
   printf("\n");  
  
}  
  
void sort_german(void * Dummy)  
{  
   sort_array(array1, 6, locale(GERMAN_LOCALE));  
}  
  
void sort_spanish(void * Dummy)  
{     
   sort_array(array2, 3, locale(SPANISH_LOCALE));       
}  
  
void sort_english(void * Dummy)  
{     
   sort_array(array3, 3, locale(ENGLISH_LOCALE));     
}  
  
int main( )  
{  
  
   int i;  
   HANDLE threads[3];  
  
   printf("Unsorted input:\n");  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
   // Create several threads that perform sorts in different  
   // languages at the same time.   
  
   threads[0] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_german , 0, NULL));  
   threads[1] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_spanish, 0, NULL));  
   threads[2] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_english, 0, NULL));  
  
   for (i = 0; i < 3; i++)  
   {  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
      {  
         printf("Error creating threads.\n");  
         exit(1);  
      }  
   }  
  
   // Wait until all threads have terminated.  
   WaitForMultipleObjects(3, threads, true, INFINITE);  
  
   printf("Sorted output: \n");  
  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Unsorted input:  
weiß weis annehmen weizen Zeit weit   
Español España espantado   
table tableux tablet   
Sorted output:   
annehmen weiß weis weit weizen Zeit   
España Español espantado   
table tablet tableux  
```  
  
## <a name="see-also"></a>参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)