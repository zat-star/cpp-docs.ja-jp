---
title: "puts、_putws | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putws
- puts
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
- _putts
- _putws
- puts
dev_langs: C++
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e05b0560032d79e5e69a1cafe8669c79160b8e1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="puts-putws"></a>puts、_putws
**stdout** に文字列を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int puts(  
   const char *str   
);  
int _putws(  
   const wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 出力する文字列。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、0 以上の値を返します。 `puts` が失敗した場合、`EOF` を返します。`_putws` が失敗した場合、**WEOF** を返します。 `str` が null ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EOF` または **WEOF** を返します。  
  
 これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `puts` 関数は、`str` を標準出力ストリーム **stdout** に書き込みます。出力ストリームで文字列の終端の null 文字 ('\0') は改行文字 ('\n') に置き換えられます。  
  
 `_putws` は `puts` のワイド文字バージョンであり、ストリームが ANSI モードで開いている場合、この 2 つの関数の動作は同じです。 `puts` では、UNICODE ストリームへの出力はサポートされていません。  
  
 Windows 2000 以降では、**_putwch** は現在の CONSOLE LOCALE 設定を使用して Unicode 文字を書き出します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_putts`|`puts`|`puts`|`_putws`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`puts`|\<stdio.h>|  
|`_putws`|\<stdio.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_puts.c  
/* This program uses puts to write a string to stdout.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   puts( "Hello world from puts!" );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Hello world from puts!  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputs、fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [fgets、fgetws](../../c-runtime-library/reference/fgets-fgetws.md)