---
title: "getenv_s、_wgetenv_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getenv_s
- _wgetenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
dev_langs: C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: "42"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b714d1643ae929245f93f770fe67a87b0c75b54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="getenvs-wgetenvs"></a>getenv_s、_wgetenv_s
現在の環境から値を取得します。 これらの [getenv および _wgetenvgets](../../c-runtime-library/reference/getenv-wgetenv.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char* buffer,  
   size_t numberOfElements,  
   const char *varname   
);  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *varname   
);  
template <size_t size>  
errno_t getenv_s(   
   size_t *pReturnValue,  
   char (&buffer)[size],  
   const char *varname   
); // C++ only  
template <size_t size>  
errno_t _wgetenv_s(   
   size_t *pReturnValue,  
   wchar_t (&buffer)[size],  
   const wchar_t *varname   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pReturnValue`  
 必要なバッファー サイズ。変数が見つからない場合は 0。  
  
 `buffer`  
 環境変数の値を格納するバッファー。  
  
 `numberOfElements`  
 
          `buffer` のサイズ。  
  
 `varname`  
 環境変数名。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は 0 を返し、それ以外の場合は失敗に関するエラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`pReturnValue`|`buffer`|`numberOfElements`|`varname`|戻り値|  
|--------------------|--------------|------------------------|---------------|------------------|  
|`NULL`|任意|任意|任意|`EINVAL`|  
|任意|`NULL`|>0|任意|`EINVAL`|  
|任意|任意|任意|`NULL`|`EINVAL`|  
  
 これらのいずれかのエラー条件の場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 また、バッファーが小さすぎる場合は、`ERANGE` が返されます。 無効なパラメーター ハンドラーは呼び出されません。 必要なバッファー サイズが `pReturnValue` に書き込まれ、プログラムはより大きなバッファーを使って関数を再度呼び出せるようになります。  
  
## <a name="remarks"></a>コメント  
 `getenv_s` 関数は、環境変数のリストから `varname` を検索します。 Windows オペレーティング システムでは、`getenv_s` 関数は大文字と小文字を区別しません。 `getenv_s` と `_putenv_s` は、`_environ` グローバル変数が指す環境のコピーを使用して環境にアクセスします。 `getenv_s` は、ランタイム ライブラリからアクセスできるデータ構造体だけを対象とし、プロセス用にオペレーティング システムで作成された環境 "セグメント" は参照しません。 そのため、プログラムで [main](../../cpp/main-program-startup.md) または [wmain](../../cpp/main-program-startup.md) の引数 `envp` を使用する場合、無効な情報を取得する可能性があります。  
  
 ワイド文字を扱う場合は、`_wgetenv_s` ではなく `getenv_s` を使用します。`_wgetenv_s` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 `_wenviron` グローバル変数は `_environ` と同じですが、ワイド文字を扱えるという点で異なっています。  
  
 SBCS ASCII プログラムなどの MBCS プログラムでは、環境がマルチバイト文字列で構成されているため、`_wenviron` の初期値は `NULL` です。 その後、`_wputenv` を最初に呼び出すとき、または (MBCS) 環境が既に存在する場合に `_wgetenv_s` を最初に呼び出すとき、対応するワイド文字列環境が作成され、その後は作成されたワイド文字列環境が `_wenviron` によって参照されます。  
  
 同様に、Unicode (`(_wmain`) プログラムでは、環境がワイド文字列で構成されているため、`_environ` の初期値は `NULL` です。 その後、`_putenv` を最初に呼び出すとき、または (Unicode) 環境が既に存在する場合に `getenv_s` を最初に呼び出すときは、対応する MBCS 環境が作成され、その後は作成された MBCS 環境が `_environ` によって参照されます。  
  
 2 つの環境のコピー (MBCS および Unicode) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。 たとえば、`_putenv` を呼び出す場合は、2 つの環境文字列が対応するように `_wputenv` も自動的に呼び出されます。  
  
> [!CAUTION]
>  まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。 これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないために発生します。 詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。  
  
> [!NOTE]
>  `_putenv_s` 系関数と `_getenv_s` 系関数はスレッド セーフではありません。 `_putenv_s` が文字列を変更している間に `_getenv_s` が文字列ポインターを返すことがあり、これはランダム エラーの原因になります。 これらの関数の呼び出しが同期されていることを確認する必要があります。  
  
 C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tgetenv_s`|`getenv_s`|`getenv_s`|`_wgetenv_s`|  
  
 `TZ` 環境変数の値を確認または変更するには、必要に応じて、`getenv_s`、`_putenv`、および `_tzset` を使用します。 `TZ` の詳細については、「[_tzset](../../c-runtime-library/reference/tzset.md)」および「[_daylight、timezone、および _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`getenv_s`|\<stdlib.h>|  
|`_wgetenv_s`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_getenv_s.c  
// This program uses getenv_s to retrieve  
// the LIB environment variable and then uses  
// _putenv to change it to a new value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* libvar;  
   size_t requiredSize;  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
   if (requiredSize == 0)  
   {  
      printf("LIB doesn't exist!\n");  
      exit(1);  
   }  
  
   libvar = (char*) malloc(requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the value of the LIB environment variable.  
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "Original LIB variable is: %s\n", libvar );  
  
   // Attempt to change path. Note that this only affects  
   // the environment variable of the current process. The command  
   // processor's environment is not changed.  
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );  
  
   getenv_s( &requiredSize, NULL, 0, "LIB");  
  
   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));  
   if (!libvar)  
   {  
      printf("Failed to allocate memory!\n");  
      exit(1);  
   }  
  
   // Get the new value of the LIB environment variable.   
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );  
  
   printf( "New LIB variable is: %s\n", libvar );  
  
   free(libvar);  
}  
```  
  
```Output  
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib  
New LIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [環境定数](../../c-runtime-library/environmental-constants.md)   
 [_putenv、_wputenv](../../c-runtime-library/reference/putenv-wputenv.md)   
 [_dupenv_s、_wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md)