---
title: "_makepath_s、_wmakepath_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wmakepath_s
- _makepath_s
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
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
dev_langs:
- C++
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bef7cdbd58ba21396c78a1945e272e0a0e1baa4d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="makepaths-wmakepaths"></a>_makepath_s、_wmakepath_s
コンポーネントからパス名を作成します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_makepath、_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `path`  
 完全なパスのバッファー。  
  
 [入力] `sizeInWords`  
 バッファーのサイズ (単語単位)。  
  
 [入力] `sizeInBytes`  
 バッファーのサイズ (バイト単位)。  
  
 [入力] `drive`  
 必要なドライブに対応する文字 (A、B など) と、この後に続くオプションのコロンを含んでいます。 `_makepath_s` ではコロンが見つからない場合、合成されるパスに自動的にコロンが挿入されます。 `drive` が `NULL` であるか空の文字列へのポインターである場合、合成された `path` 文字列にドライブ文字は含まれません。  
  
 [入力] `dir`  
 ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能で、フォワード スラッシュ (/) またはバックスラッシュ (\\) のいずれかまたは両方が、単一の `dir` 引数内で使用できます。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 `dir` が `NULL` であるか空の文字列へのポインターである場合、合成された `path` 文字列にディレクトリ パスは挿入されません。  
  
 [入力] `fname`  
 ファイル名拡張子を付けないベース ファイル名が含まれています。 `fname` が `NULL` であるか空の文字列へのポインターである場合、合成された `path` 文字列にファイル名は挿入されません。  
  
 [入力] `ext`  
 先行するピリオド (.) の有無を問わず、実際のファイル名拡張子が含まれています。 `ext` にピリオドが含まれていない場合は、`_makepath_s` によってピリオドが自動的に挿入されます。 `ext` が `NULL` であるか空の文字列へのポインターである場合、合成された `path` 文字列に拡張子は挿入されません。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`path`|`sizeInWords` / `sizeInBytes`|Return|`path` の内容|  
|------------|------------------------------------|------------|------------------------|  
|`NULL`|任意|`EINVAL`|変更されない|  
|任意|<= 0|`EINVAL`|変更されない|  
  
 上記のいずれかのエラー条件が発生すると、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `EINVAL` が返されます。 `NULL` は、`drive`、`fname`、`ext` の各パラメーターで許可されています。 これらのパラメーターが Null ポインターまたは空の文字列である場合の動作の詳細については、「コメント」セクションを参照してください。  
  
## <a name="remarks"></a>コメント  
 `_makepath_s` 関数は個別のコンポーネントから合成パス文字列を作成し、`path` に結果を格納します。 `path` に格納される可能性があるのは、ドライブ文字、ディレクトリ パス、ファイル名、ファイル名拡張子です。 `_wmakepath_s` は `_makepath_s` のワイド文字バージョンであり、`_wmakepath_s` の引数はワイド文字列です。 それ以外では、`_wmakepath_s` と `_makepath_s` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 `path` 引数は、完全なパスを保持するのに十分な大きさの空のバッファーを指す必要があります。 合成 `path` は、Stdlib.h で定義されている、`_MAX_PATH` 定数以下にする必要があります。  
  
 path が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 さらに、`errno` が `EINVAL` に設定されます。 その他のすべてのパラメーターに対しては `NULL` 値が許可されます。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).を使用します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_makepath_s`|\<stdlib.h>|  
|`_wmakepath_s`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_fullpath、_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath_s、_wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [_makepath、_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)