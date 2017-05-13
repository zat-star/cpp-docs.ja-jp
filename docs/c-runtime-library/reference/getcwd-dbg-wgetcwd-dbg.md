---
title: "_getcwd_dbg、_wgetcwd_dbg | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9814916e32878a1e1a11f534fce64aeaf2f6a57e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg、_wgetcwd_dbg
[_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) 関数のデバッグ バージョン (デバッグ中のみ使用可能)。  
  
## <a name="syntax"></a>構文  
  
```  
char *_getcwd_dbg(   
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetcwd_dbg(   
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 パスの格納場所。  
  
 `maxlen`  
 文字数でのパスの最大長。`char` の場合は `_getcwd_dbg`、および `wchar_t` の場合は `_wgetcwd_dbg`。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
## <a name="return-value"></a>戻り値  
 `buffer`へのポインターを返します。 `NULL` 戻り値はエラーを示し、 `errno` は、 `ENOMEM`に設定され、 `maxlen` バイトを割り当てるのにメモリが不足している ( `NULL` の引数が `buffer`として指定されている場合) ことを示すか、または `ERANGE`に設定され、パスが `maxlen` 文字より長いことを示します。  
  
 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_getcwd_dbg`と`_wgetcwd_dbg`関数と同じ`_getcwd`と`_wgetcwd`する点を除いてときに、`_DEBUG`が定義されている場合、これらの関数を使用してデバッグ バージョンの`malloc`と`_malloc_dbg`メモリを割り当てる場合`NULL`は最初のパラメーターとして渡されます。 詳細については、「[_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)」をご覧ください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、`_CRTDBG_MAP_ALLOC` フラグを定義できます。 `_CRTDBG_MAP_ALLOC` が定義されている場合、`_getcwd` および `_wgetcwd` の呼び出しはそれぞれ `_getcwd_dbg` および `_wgetcwd_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。 そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。  
  
## <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h>|  
|`_wgetcwd_dbg`|\<crtdbg.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
