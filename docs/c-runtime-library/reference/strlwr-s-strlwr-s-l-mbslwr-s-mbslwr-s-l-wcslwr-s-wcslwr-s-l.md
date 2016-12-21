---
title: "_strlwr_s、_strlwr_s_l、_mbslwr_s、_mbslwr_s_l、_wcslwr_s、_wcslwr_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strlwr_s_l"
  - "_mbslwr_s_l"
  - "_mbslwr_s"
  - "_wcslwr_s"
  - "_strlwr_s"
  - "_wcslwr_s_l"
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
  - "_strlwr_s_l"
  - "_strlwr_s"
  - "mbslwr_s_l"
  - "strlwr_s_l"
  - "_wcslwr_s"
  - "strlwr_s"
  - "mbslwr_s"
  - "_wcslwr_s_l"
  - "wcslwr_s_l"
  - "_tcslwr_s"
  - "_tcslwr_s_l"
  - "_mbslwr_s_l"
  - "wcslwr_s"
  - "_mbslwr_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbslwr_s 関数"
  - "_mbslwr_s_l 関数"
  - "_strlwr_s 関数"
  - "_strlwr_s_l 関数"
  - "_tcslwr_s 関数"
  - "_tcslwr_s_l 関数"
  - "_wcslwr_s 関数"
  - "_wcslwr_s_l 関数"
  - "case, 変換"
  - "変換 (大文字小文字を), CRT 関数"
  - "mbslwr_s 関数"
  - "mbslwr_s_l 関数"
  - "文字列変換 [C++], case"
  - "文字列 [C++], case"
  - "文字列 [C++], 変換 (大文字小文字を)"
  - "strlwr_s 関数"
  - "strlwr_s_l 関数"
  - "tcslwr_s 関数"
  - "tcslwr_s_l 関数"
  - "wcslwr_s 関数"
  - "wcslwr_s_l 関数"
ms.assetid: 4883d31b-bdac-4049-83a1-91dfdeceee79
caps.latest.revision: 42
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strlwr_s、_strlwr_s_l、_mbslwr_s、_mbslwr_s_l、_wcslwr_s、_wcslwr_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のロケールまたは渡されたロケール オブジェクトを使用して、文字列を小文字に変換します。  [\_strlwr、\_wcslwr、\_mbslwr、\_strlwr\_l、\_wcslwr\_l、\_mbslwr\_l](../Topic/_strlwr,%20_wcslwr,%20_mbslwr,%20_strlwr_l,%20_wcslwr_l,%20_mbslwr_l.md) のこれらのバージョンは、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  `_mbslwr_s` および `_mbslwr_s_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
errno_t _strlwr_s(  
   char *str,  
   size_t numberOfElements  
);  
errno_t _strlwr_s_l(  
   char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _mbslwr_s(  
   unsigned char *str,  
   size_t numberOfElements  
);  
errno_t _mbslwr_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
errno_t _wcslwr_s(  
   wchar_t *str,  
   size_t numberOfElements  
);  
errno_t _wcslwr_s_l(  
   wchar_t *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _strlwr_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _strlwr_s_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbslwr_s(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _mbslwr_s_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _wcslwr_s(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wcslwr_s_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### パラメーター  
 `str`  
 小文字に変換する、NULL で終わる文字列。  
  
 `numberOfElements`  
 バッファーのサイズ。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合は 0 以外のエラー コードを返します。  
  
 これらの関数では、パラメーターの検証が行われます。  `str` が null で終わる有効な文字列でない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  `numberOfElements` が文字列の長さ未満の場合も、関数は `EINVAL` 返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 `_strlwr_s` 関数は、`str` 内の大文字を同じ位置で小文字に変換します。  `_mbslwr_s` 関数は、`_strlwr_s` 関数のマルチバイト文字バージョンで、`_strlwr_s` は `_wcslwr_s` のワイド文字バージョンです。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcslwr_s`|`_strlwr_s`|`_mbslwr_s`|`_wcslwr_s`|  
|`_tcslwr_s_l`|`_strlwr_s_l`|`_mbslwr_s_l`|`_wcslwr_s_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strlwr_s`, `_strlwr_s_l`|\<string.h\>|  
|`_mbslwr_s`, `_mbslwr_s_l`|\<mbstring.h\>|  
|`_wcslwr_s`, `_wcslwr_s_l`|\<string.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_strlwr_s.cpp  
// This program uses _strlwr_s and _strupr_s to create  
// uppercase and lowercase copies of a mixed-case string.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main()  
{  
   char str[] = "The String to End All Strings!";  
   char *copy1, *copy2;  
   errno_t err;  
  
   err = _strlwr_s( copy1 = _strdup(str), strlen(str) + 1);  
   err = _strupr_s( copy2 = _strdup(str), strlen(str) + 1);  
  
   printf( "Mixed: %s\n", str );  
   printf( "Lower: %s\n", copy1 );  
   printf( "Upper: %s\n", copy2 );  
  
   free( copy1 );  
   free( copy2 );  
  
   return 0;  
}  
```  
  
  **混在: The String to End All Strings\!**  
**小文字: the string to end all strings\!**  
**大文字: THE STRING TO END ALL STRINGS\!**   
## 同等の .NET Framework 関数  
 [System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strupr\_s、\_strupr\_s\_l、\_mbsupr\_s、\_mbsupr\_s\_l、\_wcsupr\_s、\_wcsupr\_s\_l](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)