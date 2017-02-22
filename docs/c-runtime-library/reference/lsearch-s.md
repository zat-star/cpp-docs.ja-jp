---
title: "_lsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch_s"
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
  - "_lsearch_s"
  - "lsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lsearch_s 関数"
  - "配列 [CRT], 検索"
  - "キー, 検索 (配列の中で)"
  - "リニア サーチ"
  - "lsearch_s 関数"
  - "検索, リニア"
  - "値, 検索"
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _lsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値のリニア サーチを実行します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_lsearch](../../c-runtime-library/reference/lsearch.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索する配列のベースへのポインター。  
  
 `num`  
 要素の数。  
  
 `size`  
 バイトの各配列要素のサイズ。  
  
 `compare`  
 比較ルーチンへのポインター。  2 番目のパラメーターは、検索のキーへのポインターです。  3 番目のパラメーターは、キーと比較される配列要素へのポインターです。  
  
 `context`  
 比較関数にアクセスできるオブジェクトへのポインター。  
  
## 戻り値  
 `key` がある場合は、`_lsearch_s`は、`base` で配列要素へのポインターを返します。`key`一致  `key` がない場合、`_lsearch_s`は配列の末尾に新しく追加した項目へのポインターを返します。  
  
 この関数に無効なパラメーターが渡されると、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `errno`は `EINVAL` および関数の戻り値 `NULL`に設定されます。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
### エラー条件  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|\!\= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|0|`EINVAL`|  
|任意|任意|`NULL`|an|任意|`EINVAL`|  
  
## 解説  
 `_lsearch_s` 関数は `num` 要素の配列、`width` の各バイトの値 `key` のリニア サーチを実行します。  `bsearch_s`とは異なり、`_lsearch_s` は配列が並べ替えられるように必要がありません。  `key` がない場合、`_lsearch_s` は配列の末尾に追加し、`num`をインクリメントします。  
  
 `compare` 関数は、2 種類の配列要素を比較し、指定されている値を返す関係ユーザーが指定したルーチンへのポインターです。  `compare` 関数は、最初の引数としてコンテキストへのポインターを渡します。  `_lsearch_s` は 一つ以上の時間各呼び出しの 2 種類の配列要素へのポインターを渡す検索中に `compare` を呼び出します。  `compare` は 要素を比較し、0 以外の \(要素を意味して異なるしてください\) 0 を返す必要があります \(要素を意味して同じにしてください。  
  
 `context` のポインターはオブジェクトのメンバーにアクセスする検索対象のデータ構造体がオブジェクトと `compare` 関数のニーズに含まれる場合に便利です。  たとえば、`compare` 関数のコードは適切なオブジェクト型に void なポインターにキャストし、そのオブジェクトのメンバーにアクセスできます。  `context` のポインターの操作は、静的変数の使用に関連する再入のバグを避けるには、データを `compare` 関数で使用できるようにするために追加のコンテキストを使用できるため `_lsearch_s` をより安全になります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_lsearch_s`|\<search.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lfind\_s](../Topic/_lfind_s.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)