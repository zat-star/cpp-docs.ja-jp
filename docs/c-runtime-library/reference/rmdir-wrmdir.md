---
title: "_rmdir、_wrmdir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wrmdir
- _rmdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
dev_langs: C++
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d926158275e56c6d845d73fe2d8b4092a84c096c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rmdir-wrmdir"></a>_rmdir、_wrmdir
ディレクトリを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _rmdir(  
   const char *dirname   
);  
int _wrmdir(  
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dirname`  
 削除されるディレクトリのパス。  
  
## <a name="return-value"></a>戻り値  
 ディレクトリが正常に削除された場合、これらの関数はそれぞれ 0 を返します。 戻り値-1 はエラーを示すと`errno`は、次の値のいずれかに設定します。  
  
 **ENOTEMPTY**  
 指定されたパスがディレクトリではないか、ディレクトリが空でない、またはディレクトリが現在の作業ディレクトリかルート ディレクトリのいずれかです。  
  
 `ENOENT`  
 パスが無効です。  
  
 **EACCES**  
 プログラムに、ディレクトリに対して開いているハンドルがあります。  
  
 リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_rmdir` 関数は、`dirname` によって指定されたディレクトリを削除します。 ディレクトリは空である必要があり、現在の作業ディレクトリまたはルート ディレクトリではないことが必要です。  
  
 `_wrmdir` 関数は、`_rmdir` 関数のワイド文字バージョンです。`dirname` 関数の引数 `_wrmdir` は、ワイド文字列です。 それ以外では、`_wrmdir` と `_rmdir` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_trmdir`|`_rmdir`|`_rmdir`|`_wrmdir`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_rmdir`|\<direct.h>|  
|`_wrmdir`|\<direct.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
 「[_mkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [_chdir、_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)