---
title: "_creat、_wcreat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs: C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e8f61cda7d26f75677093e2377adb29a913dd35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creat-wcreat"></a>_creat、_wcreat
新しいファイルを作成します。 `_creat` と `_wcreat` は推奨されていません。代わりに [_sopen_s、_wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) をご利用ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 新しいファイルの名前。  
  
 `pmode`  
 アクセス許可の設定。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は正常に実行された場合、作成されたファイルにファイル記述子を返します。 関数が-1 を返しますそれ以外の場合、設定と`errno`次の表に示すようにします。  
  
|`errno` の設定|説明|  
|---------------------|-----------------|  
|`EACCES`|`filename` は、既存の読み取り専用ファイルを指定するか、ファイルの代わりにディレクトリを指定します。|  
|`EMFILE`|ファイル記述子をこれ以上使用できません。|  
|`ENOENT`|指定されたファイルが見つかりませんでした。|  
  
 `filename` が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、-1 を返します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_creat` 関数は新しいファイルを作成するか、既存のファイルを開いて切り詰めます。 `_wcreat` 関数は、`_creat` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wcreat` は、ワイド文字列です。 それ以外では、`_wcreat` と `_creat` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 `filename` により指定されたファイルが存在しない場合、所与のアクセス許可設定で新しいファイルが作成され、開くのでそれに書き込むことができます。 ファイルが既に存在し、そのアクセス許可設定で書き込みが許可される場合、`_creat` はファイルを長さ 0 に切り詰め、以前のコンテンツを破棄して開きます。ファイルに書き込むことができます。 アクセス許可設定 `pmode` は、新しく作成されたファイルにのみ適用されます。 新しいファイルは、最初に閉じた後に、指定されたアクセス許可設定を受け取ります。 整数式 `pmode` には、 に定義されている、マニフェスト定数 `_S_IWRITE` と `_S_IREAD` に一方または両方が含まれます。 両方の定数が指定されると、これらはビットごとの `OR` 演算子を使用して組み合わされます ( **&#124;** )。 `pmode` パラメーターには次のいずれかの値を設定されます。  
  
|値|定義|  
|-----------|----------------|  
|`_S_IWRITE`|書き込みが許可されます。|  
|`_S_IREAD`|読み取りが許可されます。|  
|`_S_IREAD &#124; _S_IWRITE`|読み取りと書き込みが許可されます。|  
  
 書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 ファイルはすべて常に読み取り可能です。書き込みのみのアクセス許可を与えることはできません。 `_S_IWRITE` モードと `_S_IREAD | _S_IWRITE` モードは同じになります。 `_creat` を利用して開くファイルは、`_SH_DENYNO` により常に互換性モード ([_sopen](../../c-runtime-library/reference/sopen-wsopen.md) 参照) で開きます。  
  
 `_creat` では、アクセス許可を設定する前に、現在のファイル アクセス許可マスクが `pmode` に適用されます ([_umask](../../c-runtime-library/reference/umask.md) 参照)。 `_creat` は主に以前のライブラリとの互換性のための関数です。 `oflag` パラメーターに `_O_CREAT` と `_O_TRUNC` を指定して `_open` を呼び出すことは `_creat` と同じであり、新しいコードの場合に推奨されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|  
|`_wcreat`|\<io.h> または \<wchar.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>関連項目  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_chmod、_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [dup、dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen、_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)