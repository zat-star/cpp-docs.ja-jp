---
title: _setmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _setmode
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
- _setmode
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d98825dfa2cbe6a38fc945fa9cfaaca4679cdb8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setmode"></a>_setmode
ファイルの変換モードを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _setmode (  
   int fd,  
   int mode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 ファイル記述子。  
  
 `mode`  
 新しい変換モード。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、前の変換モードを返します。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行の続行には、この関数は-1 を返しセットが許可された場合`errno`いずれかに`EBADF`、無効なファイル記述子を示すまたは`EINVAL`、無効なことを示します`mode`引数。  
  
 リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_setmode` 関数は、`mode` で指定されたファイルの変換モードを `fd` に設定します。 `_O_TEXT` として `mode` を渡すと、テキスト (変換) モードが設定されます。 キャリッジ リターンとライン フィード (CR-LF) の組み合わせは、1 つのライン フィード文字の入力に変換されます。 ライン フィード文字は、出力時に CR-LF の組み合わせに変換されます。 `_O_BINARY` を渡すと、バイナリ (未変換) モードが設定され、このモードではこれらの変換は抑制されます。  
  
 渡すことも`_O_U16TEXT`、 `_O_U8TEXT`、または`_O_WTEXT`このドキュメントの後半では、2 番目の例に示すように、Unicode モードを有効にします。 `_setmode` は、通常は `stdin` および `stdout` の既定の変換モードを変更するために使用しますが、任意のファイルで使用できます。 `_setmode` をストリームのファイル記述子に適用する場合は、ストリームに対して入力または出力操作を実行する前に `_setmode` を呼び出します。  
  
> [!CAUTION]
>  ファイル ストリームにデータを書き込む場合は、`_setmode` を使用してモードを変更する前に、[fflush](../../c-runtime-library/reference/fflush.md) を使用して明示的にコードをフラッシュします。 コードをフラッシュしないと、予期しない動作が発生することがあります。 ストリームにデータを書き込んでいない場合は、コードをフラッシュする必要はありません。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_setmode`|\<io.h>|\<fcntl.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
```Output  
'stdin' successfully changed to binary mode  
```  
  
## <a name="example"></a>例  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)