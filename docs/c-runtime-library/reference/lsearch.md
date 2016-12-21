---
title: "_lsearch | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch"
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
  - "_lsearch"
  - "lsearch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lsearch 関数"
  - "配列 [CRT], 検索"
  - "キー, 検索 (配列の中で)"
  - "リニア サーチ"
  - "lsearch 関数"
  - "検索, リニア"
  - "値, 検索"
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値のリニア サーチ;を実行します。がリストの末尾に追加します。  この関数のセキュリティが強化されたバージョンを使用できる; [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)を参照してください。  
  
## 構文  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索する配列のベースへのポインター。  
  
 `num`  
 要素の数。  
  
 `width`  
 各配列要素の幅。  
  
 `compare`  
 比較ルーチンへのポインター。  最初のパラメーターは、検索用のキーへのポインターです。  2 番目のパラメーターは、キーと比較される配列要素へのポインターです。  
  
## 戻り値  
 キーがある場合は、`_lsearch``base` で配列要素へのポインターを返します。`key`一致  キーが存在しない場合、`_lsearch` は配列の末尾に新しく追加した項目へのポインターを返します。  
  
## 解説  
 `_lsearch` 関数は `num` 要素の配列、`width` の各バイトの値 `key` のリニア サーチを実行します。  `bsearch`とは異なり、`_lsearch` は配列が並べ替えられるように必要がありません。  `key` がない場合、`_lsearch` は配列の末尾に追加し、`num`をインクリメントします。  
  
 `compare` の引数は、2 種類の配列要素を比較し、指定されている値を返す関係ユーザーが指定したルーチンへのポインターです。  `_lsearch` は 一つ以上の時間各呼び出しの 2 種類の配列要素へのポインターを渡す検索中に `compare` ルーチンを呼び出します。  `compare` は 要素を比較し、0 以外の \(要素を意味して異なるしてください\) 0 を返す必要があります \(要素を意味して同じにしてください。  
  
 この関数は、パラメーターを検証します。  `compare`、`key` または `num` が `NULL`であるか、または `base` が null になり`num` \*は 0 以外のか、`width` が小さい場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_lsearch`|\<search.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **\_lsearch の前の単語リスト: Hello bye 感謝**  
**\_lsearch の後の単語リスト: Hello BYE 感謝の追加**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)