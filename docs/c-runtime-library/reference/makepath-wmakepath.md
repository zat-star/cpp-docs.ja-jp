---
title: "_makepath、_wmakepath | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
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
ms.openlocfilehash: deb4333b36bf0b3eb2080d838ef3f23a052cf262
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="makepath-wmakepath"></a>_makepath、_wmakepath
コンポーネントからパス名を作成します。 これらの関数のセキュリティを強化したバージョンについては、「[_makepath_s、_wmakepath_s (_makepath_s、_wmakepath_s)](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 完全なパスのバッファー。  
  
 `drive`  
 必要なドライブに対応する文字 (A、B など) と、省略可能である後続のコロンを含んでいます。 `_makepath` ではコロンが見つからない場合、合成されるパスに自動的にコロンが挿入されます。 `drive` が `NULL` であるか空の文字列へのポインターである場合、合成される `path` 文字列にドライブ文字は含まれません。  
  
 `dir`  
 ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能で、フォワード スラッシュ (/) またはバックスラッシュ (\\) のいずれかまたは両方が、単一の `dir` 引数内で使用できます。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 `dir` が `NULL` であるか空の文字列へのポインターである場合、合成される `path` 文字列にディレクトリ パスは挿入されません。  
  
 `fname`  
 ファイル名拡張子がないベース ファイル名が含まれています。 `fname` が `NULL` であるか空の文字列へのポインターである場合、合成される `path` 文字列にファイル名は挿入されません。  
  
 `ext`  
 実際のファイル名拡張子が含まれており、先頭のピリオド (.) の有無は問いません。 `ext` にピリオドが含まれていない場合は、`_makepath` によってピリオドが自動的に挿入されます。 `ext` が `NULL` であるか空の文字列へのポインターである場合、合成される `path` 文字列に拡張子は挿入されません。  
  
## <a name="remarks"></a>コメント  
 `_makepath` 関数は個別のコンポーネントから合成パス文字列を作成し、`path` に結果を格納します。 `path` に格納される可能性があるのは、ドライブ文字、ディレクトリ パス、ファイル名、ファイル名拡張子です。 `_wmakepath` は `_makepath` のワイド文字バージョンであり、`_wmakepath` の引数はワイド文字列です。 それ以外では、`_wmakepath` と `_makepath` の動作は同じです。  
  
 **セキュリティに関するメモ** null で終わる文字列を使用してください。 バッファー オーバーランを防ぐために、null で終わる文字列は `path` バッファーのサイズを超えないようにしてください。 `_makepath` では、合成パス文字列が `_MAX_PATH` を超えていないことを確認できません。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 `path` 引数は、完全なパスを保持するのに十分な大きさの空のバッファーを指す必要があります。 合成 `path` は、Stdlib.h で定義されている、`_MAX_PATH` 定数以下にする必要があります。  
  
 path が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 さらに、`errno` が `EINVAL` に設定されます。 その他のすべてのパラメーターに対しては `NULL` 値が許可されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h> または \<wchar.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
```Output  
Path created with _makepath: c:\sample\crt\makepath.c  
  
Path extracted with _splitpath:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: makepath  
  Ext: .c  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_fullpath、_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath、_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s、_wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)
