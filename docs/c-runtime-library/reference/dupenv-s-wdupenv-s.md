---
title: "_dupenv_s、_wdupenv_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s
- _wdupenv_s
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
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs:
- C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: 16
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
ms.openlocfilehash: 3332c33e2d2b79106cf88f143fe99cb91bbce670
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s、_wdupenv_s
現在の環境から値を取得します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _dupenv_s(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname  
);  
errno_t _wdupenv_s(  
   wchar_t **buffer,  
   size_t *numberOfElements,  
   const wchar_t *varname  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 変数の値を格納するバッファー。  
  
 `numberOfElements`  
 
          `buffer` のサイズ。  
  
 `varname`  
 環境変数名。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
 これらの関数は、パラメーターを検証します。`buffer` または `varname` が `NULL` の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 十分なメモリを割り当てられない場合、これらの関数は `buffer` を `NULL` に、`numberOfElements` を 0 に設定し、`ENOMEM` を返します。  
  
## <a name="remarks"></a>コメント  
 `_dupenv_s` 関数は、環境変数のリストから `varname` を検索します。 変数が見つかると、`_dupenv_s` はバッファーを割り当てて変数の値をバッファーにコピーします。 バッファーのアドレスと長さが `buffer` および `numberOfElements` で返されます。 バッファー自体を割り当てる点で、`_dupenv_s` 関数は [getenv_s、_wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) より便利な代替関数として使用できます。  
  
> [!NOTE]
>  [free](../../c-runtime-library/reference/free.md) の呼び出しによるメモリの解放は、呼び出し元プログラムが行います。  
  
 変数が見つからない場合は、`buffer` が `NULL` に、`numberOfElements` が 0 に設定され、戻り値が 0 になります。これは、この状況がエラー状況と見なされないためです。  
  
 バッファーのサイズを考慮しない場合は、`NULL` に `numberOfElements` を渡すことができます。  
  
 Windows オペレーティング システムでは、`_dupenv_s` 関数は大文字と小文字を区別しません。 `_dupenv_s` 関数は、`_environ` グローバル変数が指す環境のコピーを使用して環境にアクセスします。 `_environ` については、「[getenv_s、_wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)」の「コメント」をご覧ください。  
  
 `buffer` の値は、環境変数の値のコピーです。この値を変更しても環境には影響しません。 環境変数の値を変更するには、[_putenv_s、_wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md) 関数を使います。  
  
 `_wdupenv_s` は `_dupenv_s` のワイド文字バージョンで、`_wdupenv_s` の引数はワイド文字列です。 `_wenviron` グローバル変数は `_environ` と同じですが、ワイド文字を扱えるという点で異なっています。 `_wenviron` について詳しくは、「[getenv_s、_wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)」の「コメント」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_dupenv_s`|\<stdlib.h>|  
|`_wdupenv_s`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [環境定数](../../c-runtime-library/environmental-constants.md)   
 [_dupenv_s_dbg、_wdupenv_s_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv_s、_wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [putenv_s、_wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)
