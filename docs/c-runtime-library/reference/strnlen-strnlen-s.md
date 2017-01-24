---
title: "strnlen、strnlen_s、wcsnlen、wcsnlen_s、_mbsnlen、_mbsnlen_l、_mbstrnlen、_mbstrnlen_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsnlen"
  - "strnlen_s"
  - "_mbstrnlen"
  - "_mbsnlen_l"
  - "_mbstrnlen_l"
  - "strnlen"
  - "wcsnlen_s"
  - "_mbsnlen"
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
  - "wcsnlen"
  - "strnlen_s"
  - "_mbsnlen"
  - "_mbsnlen_l"
  - "_tcsnlen"
  - "_tcscnlen"
  - "_mbstrnlen_l"
  - "wcsnlen_s"
  - "_mbstrnlen"
  - "strnlen"
  - "_tcscnlen_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnlen 関数"
  - "_mbsnlen_l 関数"
  - "_mbstrnlen 関数"
  - "_mbstrnlen_l 関数"
  - "_tcscnlen 関数"
  - "_tcscnlen_l 関数"
  - "_tcsnlen 関数"
  - "長さ, 文字列"
  - "mbsnlen 関数"
  - "mbsnlen_l 関数"
  - "mbstrnlen 関数"
  - "mbstrnlen_l 関数"
  - "文字列長"
  - "strnlen 関数"
  - "strnlen_l 関数"
  - "strnlen_s 関数"
  - "wcsnlen 関数"
  - "wcsnlen_l 関数"
  - "wcsnlen_s 関数"
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
caps.latest.revision: 35
caps.handback.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strnlen、strnlen_s、wcsnlen、wcsnlen_s、_mbsnlen、_mbsnlen_l、_mbstrnlen、_mbstrnlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のロケールまたは渡されたロケールを使用して、文字列の長さを取得します。  これらは、[strlen、wcslen、\_mbslen、\_mbslen\_l、\_mbstrlen、\_mbstrlen\_l](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md) のセキュリティを強化したバージョンです。  
  
> [!IMPORTANT]
>  `_mbsnlen`、`_mbsnlen_l`、`_mbstrnlen`、および `_mbstrnlen_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
size_t strnlen(  
   const char *str,  
   size_t numberOfElements   
);  
size_t strnlen_s(  
   const char *str,  
   size_t numberOfElements   
);  
size_t wcsnlen(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t wcsnlen_s(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen(  
   const unsigned char *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen_l(  
   const unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
size_t _mbstrnlen(  
   const char *str,  
   size_t numberOfElements  
);  
size_t _mbstrnlen_l(  
   const char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 NULL で終わる文字列。  
  
 `numberOfElements`  
 文字列バッファーのサイズ。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの関数は、文字列内の文字数を返します \(終端の null 文字は含まれません\)。  文字列 \(または `numberOfElements` の場合はワイド文字\) の最初の `wcsnlen` バイト内に null 終端文字がない場合は、エラー状況を示す `numberOfElements` が返されます。null で終わる文字列の長さは、厳密に `numberOfElements` 未満になります。  
  
 `_mbstrnlen` および `_mbstrnlen_l` は、文字列に無効なマルチバイト文字が含まれている場合は \-1 を返します。  
  
## 解説  
  
> [!NOTE]
>  `strnlen` は `strlen` に代わるものではありません。`strnlen` は、既知のサイズのバッファー \(ネットワーク パケットなど\) 内の受信した信頼できないデータのサイズを計算するためにのみ使用することを目的としています。  `strnlen` は長さを計算しますが、文字列に終端文字がない場合にバッファーの末尾を超えません。  その他の状況では、`strlen` を使用します。  \(同じことが `wcsnlen`、`_mbsnlen`、および `_mbstrnlen` に適用されます\)。  
  
 これらの各関数は、`str` 内の文字数を返します \(終端の null 文字は含まれません\)。  ただし、`strnlen` および `strnlen_s` は文字列を 1 バイト文字列として扱うため、マルチバイト文字が含まれている場合でも、戻り値は常にバイト数と同じです。  `wcsnlen` および `wcsnlen_s` は、それぞれ `strnlen` および `strnlen_s` のワイド文字バージョンです。`wcsnlen` および `wcsnlen_s` の引数はワイド文字列で、文字数はワイド文字単位です。  それ以外では、`wcsnlen` と `strnlen` の動作は同じです。`strnlen_s` と `wcsnlen_s` の場合も同様です。  
  
 `strnlen`、`wcsnlen,`、および `_mbsnlen` は、パラメーターを検証しません。  `str` が `NULL` の場合、アクセス違反が発生します。  
  
 `strnlen_s` および `wcsnlen_s` は、パラメーターを検証します。  `str` が `NULL` の場合、関数は 0 を返します。  
  
 `_mbstrnlen` もそのパラメーターを検証します。  `str` が `NULL` の場合、または `numberOfElements` が `INT_MAX` を超える場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、`_mbstrnlen` は無効なパラメーター例外を生成します。  実行の継続が許可された場合、`_mbstrnlen` は `errno` を `EINVAL` に設定し、\-1 を返します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsnlen`|`strnlen`|`strnlen`|`wcsnlen`|  
|`_tcscnlen`|`strnlen`|`_mbsnlen`|`wcsnlen`|  
|`_tcscnlen_l`|`strnlen`|`_mbsnlen_l`|`wcsnlen`|  
  
 `_mbsnlen` と `_mbstrnlen` は、マルチバイト文字列のマルチバイト文字数を返します。  `_mbsnlen` は、現在使用中のマルチバイトのコード ページに従って、または渡されたロケールに従って、マルチバイト文字のシーケンスを認識します。マルチバイト文字の有効性はテストしません。  `_mbstrnlen` は、マルチバイト文字の有効性をテストし、マルチバイト文字のシーケンスを認識します。  `_mbstrnlen` に渡された文字列に無効なマルチバイト文字が含まれている場合、`errno` は `EILSEQ` に設定されます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないバージョンがこのロケールに依存する動作に現在のロケールを使用し、`_l` サフィックスが付いているバージョンが渡されたロケール パラメーターを代わりに使用する点を除いて、これらの関数のバージョンは同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strnlen`, `strnlen_s`|\<string.h\>|  
|`wcsnlen`, `wcsnlen_s`|\<string.h\> または \<wchar.h\>|  
|`_mbsnlen`, `_mbsnlen_l`|\<mbstring.h\>|  
|`_mbstrnlen`, `_mbstrnlen_l`|\<stdlib.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strnlen.c  
  
#include <string.h>  
  
int main()  
{  
   // str1 is 82 characters long. str2 is 159 characters long   
  
   char* str1 = "The length of a string is the number of characters\n"  
               "excluding the terminating null.";  
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"  
                "than the maximum size specified, the maximum size is\n"  
                "returned rather than the actual size of the string.";  
   size_t len;  
   size_t maxsize = 100;  
  
   len = strnlen(str1, maxsize);  
   printf("%s\n Length: %d \n\n", str1, len);  
  
   len = strnlen(str2, maxsize);  
   printf("%s\n Length: %d \n", str2, len);  
}  
```  
  
  **The length of a string is the number of characters**  
**excluding the terminating null.  Length: 82**   
**strnlen takes a maximum size.  If the string is longer**  
**than the maximum size specified, the maximum size is**  
**returned rather than the actual size of the string.  Length: 100**    
## 同等の .NET Framework 関数  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、\_mbsncmp、\_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)   
 [strrchr、wcsrchr、\_mbsrchr、\_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn、wcsspn、\_mbsspn、\_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)