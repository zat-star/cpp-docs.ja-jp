---
title: "strcat、wcscat、_mbscat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbscat"
  - "wcscat"
  - "strcat"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbscat"
  - "_ftcscat"
  - "_tcscat"
  - "strcat"
  - "wcscat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscat 関数"
  - "_mbscat 関数"
  - "_tcscat 関数"
  - "追加 (文字列を)"
  - "連結 (文字列を)"
  - "ftcscat 関数"
  - "mbscat 関数"
  - "strcat 関数"
  - "文字列 [C++], 追加"
  - "文字列 [C++], 連結"
  - "tcscat 関数"
  - "wcscat 関数"
ms.assetid: c89c4ef1-817a-44ff-a229-fe22d06ba78a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# strcat、wcscat、_mbscat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を追加します。  これらの関数のセキュリティを強化したバージョンについては、「[strcat\_s、wcscat\_s、\_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)」を参照してください。  
  
> [!IMPORTANT]
>  `_mbscat_s` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 `strDestination`  
 NULL で終わる追加先の文字列。  
  
 `strSource`  
 NULL で終わる元の文字列。  
  
## 戻り値  
 これらの関数は、コピー先文字列 \(`strDestination`\) を返します。  エラーを示す戻り値は予約されていません。  
  
## 解説  
 `strcat` 関数は、`strSource` を `strDestination` に追加し、結果の文字列の終端に null 文字を付けます。  `strSource` の先頭の文字は、`strDestination` の終端の null 文字を上書きします。  コピー元とコピー先の文字列が重なり合っている場合の `strcat` 関数の動作は未定義です。  
  
> [!IMPORTANT]
>  `strcat` が、`strSource` を追加する前に、`strDestination` に十分な領域があるかどうかを確認しないことが、バッファー オーバーランの潜在的な原因です。  代わりに [strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) の使用を検討してください。  
  
 `wcscat` 関数と `_mbscat` 関数は、`strcat` 関数のワイド文字バージョンとマルチバイト文字バージョンです。  `wcscat` 関数の引数と戻り値はワイド文字列で、`_mbscat` 関数の引数と戻り値はマルチバイト文字列です。  それ以外では、これらの関数の動作は同じです。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcscat`|`strcat`|`_mbscat`|`wcscat`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strcat`|\<string.h\>|  
|`wcscat`|\<string.h\> または \<wchar.h\>|  
|`_mbscat`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)