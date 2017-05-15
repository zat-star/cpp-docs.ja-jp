---
title: _lsearch_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch_s
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
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 4969a12a821040c007a43248dc15927ee9f6ab40
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="lsearchs"></a>_lsearch_s
値の線形探索を実行します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_lsearch](../../c-runtime-library/reference/lsearch.md) です。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `key`  
 検索するオブジェクト。  
  
 `base`  
 検索する配列のベースへのポインター。  
  
 `num`  
 要素の数。  
  
 `size`  
 バイト単位での配列の各要素のサイズ。  
  
 `compare`  
 比較ルーチンへのポインター。 2 番目のパラメーターは、検索用のキーへのポインターです。 3 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。  
  
 `context`  
 比較関数内でアクセスされることのあるオブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `key` が見つかった場合、`_lsearch_s` は `key` と一致する `base` の配列要素のポインターを返します。 `key` が見つからない場合、`_lsearch_s` は新しく追加された項目へのポインターを配列の末尾に返します。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|任意|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|任意|!= 0|任意|`EINVAL`|  
|任意|任意|任意|任意|ゼロ|`EINVAL`|  
|任意|任意|`NULL`|1 つ|任意|`EINVAL`|  
  
## <a name="remarks"></a>コメント  
 `_lsearch_s` 関数は、`num` 要素の配列の値 `key` に対する一方向の検索を、`width` バイトごとに実行します。 `bsearch_s` とは異なり、`_lsearch_s` では配列を並べ替える必要がありません。 `key` が見つからない場合、`_lsearch_s` によって配列の末尾に追加され `num` がインクリメントされます。  
  
 `compare` 関数は、2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。 `compare` 関数はまた、最初の引数としてコンテキストへのポインターを受け取ります。 `_lsearch_s` は検索中に `compare` を 1 回以上呼び出し、各呼び出しにおいて 2 つの配列要素へのポインターを渡します。 `compare` は要素を比較し、ゼロ以外 (要素が異なる場合) または 0 (要素が同じ場合) を返す必要があります。  
  
 `context` ポインターは、検索対象のデータ構造体がオブジェクトの一部であり、`compare` 関数でオブジェクトのメンバーにアクセスする必要がある場合に役立ちます。 たとえば、`compare` 関数のコードは void ポインターを該当するオブジェクト型にキャストして、そのオブジェクトのメンバーにアクセスできます。 `context` ポインターを追加すると、`compare` 関数でデータを使用可能にする静的変数を使用する場合の再入バグを回避するために、追加のコンテキストを使用できるので、`_lsearch_s` がより安全になります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)
