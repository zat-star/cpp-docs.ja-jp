---
title: "strcat、wcscat、_mbscat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbscat
- wcscat
- strcat
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbscat
- _ftcscat
- _tcscat
- strcat
- wcscat
dev_langs: C++
helpviewer_keywords:
- concatenating strings
- mbscat function
- _ftcscat function
- _tcscat function
- ftcscat function
- strcat function
- strings [C++], appending
- _mbscat function
- tcscat function
- strings [C++], concatenating
- appending strings
- wcscat function
ms.assetid: c89c4ef1-817a-44ff-a229-fe22d06ba78a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7b85ce742cb39dcb9333a4eae5959e38c4ec50a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strcat-wcscat-mbscat"></a>strcat、wcscat、_mbscat
文字列を追加します。 これらの関数にはセキュリティが強化されたバージョンがあります、「[strcat_s、wcscat_s、_mbscat_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)」をご覧ください。  
  
> [!IMPORTANT]
>  `_mbscat_s` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strcat(  
   char *strDestination,  
   const char *strSource   
);  
wchar_t *wcscat(  
   wchar_t *strDestination,  
   const wchar_t *strSource   
);  
unsigned char *_mbscat(  
   unsigned char *strDestination,  
   const unsigned char *strSource   
);  
template <size_t size>  
char *strcat(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
wchar_t *wcscat(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
unsigned char *_mbscat(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strDestination`  
 NULL で終わる追加先の文字列。  
  
 `strSource`  
 NULL で終わる元の文字列。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、コピー先文字列 (`strDestination`) を返します。 エラーを示す戻り値は予約されていません。  
  
## <a name="remarks"></a>コメント  
 `strcat` 関数は、`strSource` を `strDestination` に追加し、結果の文字列の終端に null 文字を付けます。 `strSource` の先頭の文字は、`strDestination` の終端の null 文字を上書きします。 コピー元とコピー先の文字列が重なり合っている場合の `strcat` 関数の動作は未定義です。  
  
> [!IMPORTANT]
>  `strcat` が、`strDestination` を追加する前に、`strSource` に十分な領域があるかどうかを確認しないことが、バッファー オーバーランの潜在的な原因です。 代わりに [strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) の使用を検討してください。  
  
 `wcscat` 関数と `_mbscat` 関数は、`strcat` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcscat` 関数の引数と戻り値はワイド文字列で、`_mbscat` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscat`|`strcat`|`_mbscat`|`wcscat`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`strcat`|\<string.h>|  
|`wcscat`|\<string.h> または \<wchar.h>|  
|`_mbscat`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) に関する記事の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)