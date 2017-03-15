---
title: "qsort_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort_s"
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
  - "qsort_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 並べ替え"
  - "qsort_s 関数"
  - "クイックソート アルゴリズム"
  - "配列の並べ替え"
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# qsort_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

簡単な並べ替えを実行します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[qsort](../../c-runtime-library/reference/qsort.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
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
 比較関数。  最初の引数は `context` ポインターです。  2 番目の引数は、検索用の `key` へのポインターです。  3 番目の引数は、`key` と比較される配列要素へのポインターです。  
  
 `context`  
 `compare` アクセスするルーチンに必要なオブジェクトであるコンテキストへのポインター。  
  
## 解説  
 `qsort_s` 関数は `num` 要素の配列を、`width` の各バイト並べ替えるになく並べ替えアルゴリズムを実装します。  引数 `base` は並べ替えられるよう配列のベースへのポインターです。  `qsort_s` は 並べ替えられた要素でこの配列を上書きします。  引数 `compare` は 2 個の配列要素を比較し、指定されている値を返す関係ユーザーが指定したルーチンへのポインターです。  `qsort_s` は 一つ以上の時間各呼び出しの 2 種類の配列要素へのポインターを渡す並べ替え中に `compare` ルーチンを呼び出して:  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 ルーチンは、要素を比較し、次の値のいずれか 1 つがを返す必要があります:  
  
|戻り値|説明|  
|---------|--------|  
|\< 0|`elem1` が `elem2` より小さい|  
|0|`elem2`への`elem1` の等価|  
|\> 0|`elem1` が `elem2` より大きい|  
  
 配列は、比較関数によって定義されている、昇順に並べ替えられます。  かからない順序で配列を並べ替えるには、「より大きい」と比較関数の「以下の感覚をより」に戻します。  
  
 この関数に無効なパラメーターが渡されると、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `EINVAL`への関数の戻り値と `errno` が設定されます。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
### エラー条件  
  
|key|base|compare|num|width|errno|  
|---------|----------|-------------|---------|-----------|-----------|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|\!\= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|\<\= 0|`EINVAL`|  
|任意|任意|`NULL`|任意|任意|`EINVAL`|  
  
 `qsort_s`に`qsort` と同じ動作が含まれる場合、`context` パラメーターを持ち、さらに `errno`を設定します。  `context` パラメーターを渡すと、比較関数は要素のポインターを通じてアクセスできないオブジェクトの機能やそのほかの情報にアクセスするには、オブジェクトのポインターを使用できます。  `context` パラメーターの追加は静的変数の使用によってもたらされる再入のバグを避けるため、共有情報を `compare` 関数にするために `context` を使用できるため `qsort_s`をより安全になります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`qsort_s`|\<stdlib.h と\> search.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md) のすべてのバージョン。  
  
## 使用例  
 次の例に `qsort_s`関数で `context` パラメーターを使用する方法を示します。  `context` パラメーターはスレッド セーフな並べ替えを容易にします。  スレッド セーフを確保するために同期が必要な静的変数を使用する代わりに、各並べ替えの `context` 別のパラメーターを渡します。  この例では、locale オブジェクトは `context` パラメーターとして使用されます。  
  
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
  
## 出力例  
  
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
  
## 同等の .NET Framework 関数  
 <xref:System.Collections.ArrayList.Sort%2A>  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)