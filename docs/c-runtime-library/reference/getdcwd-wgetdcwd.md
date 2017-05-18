---
title: "_getdcwd、_wgetdcwd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 03791f920619b98beec3c1bbbd33b45b550eaf7a
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd、_wgetdcwd
指定されたドライブの現在の作業ディレクトリの完全なパスを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `drive`  
 ドライブを指定する負でない整数 (0 = 既定のドライブ、1 = A、2 = B など)。  
  
 指定されたドライブが使用できない場合、またはドライブの種類 (たとえば、リムーバブル ドライブ、固定ドライブ、CD-ROM ドライブ、RAM ディスク ドライブ、ネットワーク ドライブ) を特定できない場合、「 [Parameter Validation](../../c-runtime-library/parameter-validation.md)」に説明されているように、正しくないパラメーター ハンドラーが呼び出されます。  
  
 `buffer`  
 パスの格納場所または **NULL**。  
  
 **NULL** を指定した場合、この関数は `maxlen` を使用して **maxlen**サイズ以上のバッファーを割り当てます。 `_getdcwd` の戻り値は、割り当てられたバッファーへのポインターになります。 バッファーは、 `free` を呼び出し、ポインターに渡すことによって解放できます。  
  
 `maxlen`  
 文字数でパスの最大長を指定する 0 以外の正の整数。 `char` では `_getdcwd` 、 `wchar_t` では `_wgetdcwd`。  
  
 `maxlen` が 0 以下の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  
  
## <a name="return-value"></a>戻り値  
 指定されたドライブの現在の作業ディレクトリの完全なパスを表す文字列へのポインター、またはエラーを示す `NULL`。  
  
 `buffer` を `NULL` に指定し、 `maxlen` 文字を割り当てるためのメモリが不足している場合は、エラーが発生し、 `errno` は `ENOMEM`に設定されます。 終端の null 文字を含むパスの長さが `maxlen`を超える場合、エラーが発生し、 `errno` が `ERANGE`に設定されます。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_getdcwd` 関数は、指定されたドライブの現在の作業ディレクトリの完全なパスを取得し、それを `buffer`に格納します。 現在の作業ディレクトリがルートに設定されている場合、文字列は円記号 (\\) で終わります。 現在の作業ディレクトリがルート以外のディレクトリに設定されている場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。  
  
 `_wgetdcwd` は、 `_getdcwd`のワイド文字バージョンで、その `buffer` パラメーターと戻り値はワイド文字列になります。 それ以外では、 `_wgetdcwd` と `_getdcwd` の動作は同じです。  
  
 この関数は、スレッドセーフではない **GetFullPathName**に依存しますが、スレッドセーフです。 ただし、マルチスレッド アプリケーションでこの関数と **GetFullPathName**を両方とも呼び出した場合、スレッド セーフを侵害する可能性があります。 詳しくは、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/?LinkID=150542) にアクセスし、 **GetFullPathName**。  
  
 `_nolock` サフィックスが付いているこの関数のバージョンは、スレッドセーフではなく、他のスレッドによる干渉から保護されないという点を除いて、この関数とまったく同じように動作します。 詳細については、「 [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)」を参照してください。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、 `_getdcwd` と `_wgetdcwd` への呼び出しは `_getdcwd_dbg` と `_wgetdcwd_dbg` への呼び出しに置き換えられるので、メモリ割り当てをデバッグできます。 詳しくは[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [_getdrive](../../c-runtime-library/reference/getdrive.md)の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [_chdir、_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd、_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir、_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
