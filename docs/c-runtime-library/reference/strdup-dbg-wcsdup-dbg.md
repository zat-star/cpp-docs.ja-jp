---
title: "_strdup_dbg、_wcsdup_dbg | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
apitype: DLLExport
f1_keywords:
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
dev_langs:
- C++
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: 11
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
ms.openlocfilehash: 477fca0e1849099502acea0b5d5a17fb00622b35
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg、_wcsdup_dbg
[_strdup and _wcsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md) の、`malloc` のデバッグ バージョンを使用するバージョンです。  
  
## <a name="syntax"></a>構文  
  
```  
char *_strdup_dbg(  
   const char *strSource,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wcsdup_dbg(  
   const wchar_t *strSource,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strSource`  
 NULL で終わる元の文字列。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは NULL。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または NULL。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、コピーされた文字列の格納場所へのポインター、またはストレージを割り当てることができない場合は `NULL` を返します。  
  
## <a name="remarks"></a>コメント  
 `_strdup_dbg` および `_wcsdup_dbg` 関数は `_strdup` および `_wcsdup` と同じものですが、`_DEBUG` が定義されている場合に、これらの関数は複製された文字列にメモリを割り当てるために `malloc` および `_malloc_dbg` のデバッグ バージョンを使用する点が異なります。 `_malloc_dbg` のデバッグ機能の詳細については、「[_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)」をご覧ください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、フラグ `_CRTDBG_MAP_ALLOC` を定義することができます。 `_CRTDBG_MAP_ALLOC` が定義されている場合、`_strdup` および `_wcsdup` の呼び出しはそれぞれ `_strdup_dbg` および `_wcsdup_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。 そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。 ブロック型の詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsdup_dbg`|`_strdup_dbg`|`_mbsdup`|`_wcsdup_dbg`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_strdup_dbg`, `_wcsdup_dbg`|\<crtdbg.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのデバッグ バージョン。  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_strdup、_wcsdup、_mbsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)   
 [デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
