---
title: "_splitpath_s、_wsplitpath_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wsplitpath_s
- _splitpath_s
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
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9baa71ca1a3d624c08df8ff1cbd14a9386e1b83d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s、_wsplitpath_s
パス名をコンポーネントに分割します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_splitpath、_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `path`  
 完全なパス。  
  
 [出力] `drive`  
 ドライブ文字、その後にコロン (`:`)。 ドライブ文字が不要な場合は、このパラメーターに `NULL` を渡します。  
  
 [入力] `driveNumberOfElements`  
 1 バイト文字またはワイド文字単位の `drive` バッファーのサイズ。 `drive` が `NULL` である場合、この値は 0 でなければなりません。  
  
 [出力] `dir`  
 末尾のスラッシュを含むディレクトリ パス。 スラッシュ (`/`)、バックスラッシュ (`\`)、または両方を使用できます。 ディレクトリ パスが不要な場合は、このパラメーターに `NULL` を渡します。  
  
 [入力] `dirNumberOfElements`  
 1 バイト文字またはワイド文字単位の `dir` バッファーのサイズ。 `dir` が `NULL` である場合、この値は 0 でなければなりません。  
  
 [出力] `fname`  
 拡張子なしの基本ファイル名。 ファイル名が不要な場合は、このパラメーターに `NULL` を渡します。  
  
 [入力] `nameNumberOfElements`  
 1 バイト文字またはワイド文字単位の `fname` バッファーのサイズ。 `fname` が `NULL` である場合、この値は 0 でなければなりません。  
  
 [出力] `ext`  
 先頭のピリオド (**.**) を含むファイル名の拡張子。ファイル名の拡張子が不要な場合は、このパラメーターに `NULL` を渡します。  
  
 [入力] `extNumberOfElements`  
 1 バイト文字またはワイド文字単位の `ext` バッファーのサイズ。 `ext` が `NULL` である場合、この値は 0 でなければなりません。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|条件|戻り値|  
|---------------|------------------|  
|`path` は `NULL` です|`EINVAL`|  
|`drive` が `NULL` である場合、`driveNumberOfElements` はゼロ以外です|`EINVAL`|  
|`drive` が `NULL` でない場合、`driveNumberOfElements` はゼロです|`EINVAL`|  
|`dir` が `NULL` である場合、`dirNumberOfElements` はゼロ以外です|`EINVAL`|  
|`dir` が `NULL` でない場合、`dirNumberOfElements` はゼロです|`EINVAL`|  
|`fname` が `NULL` である場合、`nameNumberOfElements` はゼロ以外です|`EINVAL`|  
|`fname` が `NULL` でない場合、`nameNumberOfElements` はゼロです|`EINVAL`|  
|`ext` が `NULL` である場合、`extNumberOfElements` はゼロ以外です|`EINVAL`|  
|`ext` が `NULL` でない場合、`extNumberOfElements` はゼロです|`EINVAL`|  
  
 上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 バッファーのいずれかが、結果を保持するには短すぎる場合、これらの関数はすべてのバッファーを空の文字列にクリアし、`errno` を `ERANGE` に設定して、`ERANGE` を返します。  
  
## <a name="remarks"></a>コメント  
 `_splitpath_s` 関数は、パスを 4 つのコンポーネントに分割します。 `_splitpath_s` は、マルチバイト文字列引数を自動的に適切に処理し、現在使用しているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 `_wsplitpath_s` は `_splitpath_s` のワイド文字バージョンであり、`_wsplitpath_s` の引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 完全なパスの各コンポーネントは別々のバッファーに格納されます。マニフェスト定数 `_MAX_DRIVE`、`_MAX_DIR`、`_MAX_FNAME`、および `_MAX_EXT` (STDLIB.H で定義される) で、各々のファイル コンポーネントの最大許容サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。  
  
 マニフェスト定数の値を次の表に示します。  
  
|name|[値]|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 完全なパスにコンポーネント (たとえばファイル名) が含まれていない場合、`_splitpath_s` は対応するバッファーに空の文字列を割り当てます。  
  
 C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).を使用します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h>|  
|`_wsplitpath_s`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[_makepath_s、_wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_splitpath、_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath、_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath、_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)