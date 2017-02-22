---
title: "_mbsnbcat、_mbsnbcat_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcat_l"
  - "_mbsnbcat"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbcat"
  - "mbsnbcat_l"
  - "_mbsnbcat"
  - "_mbsnbcat_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcat 関数"
  - "_mbsnbcat_l 関数"
  - "_tcsncat 関数"
  - "_tcsncat_l 関数"
  - "mbsnbcat 関数"
  - "mbsnbcat_l 関数"
  - "tcsncat 関数"
  - "tcsncat_l 関数"
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _mbsnbcat、_mbsnbcat_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1 つのマルチバイト文字列の先頭の最大 `n` バイトを別の文字列に追加します。  これらの関数のセキュリティを強化したバージョンについては、「[\_mbsnbcat\_s、\_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
unsigned char *_mbsnbcat(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count   
);  
unsigned char *_mbsnbcat_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
unsigned char *_mbsnbcat(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count   
); // C++ only  
template <size_t size>  
unsigned char *_mbsnbcat_l(  
   unsigned char (&dest)[size],  
   const unsigned char *src,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### パラメーター  
 `dest`  
 NULL で終わるマルチバイト文字のコピー先文字列。  
  
 `src`  
 NULL で終わるマルチバイト文字のコピー元文字列。  
  
 `count`  
 `dest` に追加される `src` のバイト数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_mbsnbcat` はコピー先文字列へのポインターを返します。  エラーを示す戻り値は予約されていません。  
  
## 解説  
 `_mbsnbcat` 関数は、`dest`に、`src` の先頭の最大 `count` バイトを追加します。  `dest` の null 文字の前のバイトが先行バイトの場合、`src` の最初のバイトはこの先行バイトをオーバーライドします。  そうでなければ、`src` の先頭のバイトは、`dest` の終端の null 文字を上書きします。  `count` バイトが追加される前に `src` に null バイトがあった場合は、\_`mbsnbcat` は null 文字までの `src` 内のすべてのバイトを追加します。  `count` が `src` の長さを超えている場合は、`src` の長さが `count` の代わりに使用されます。  結果の文字列は null 文字で終了します。  重なり合う文字列間でコピーした場合の動作は未定義です。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  関数のうちの `_mbsnbcat` バージョンは、このロケールに依存する動作に現在のロケールを使用します。`_mbsnbcat_l` バージョンは、現在のロケールの代わりにロケール パラメーターを使用することを除いて、同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 **セキュリティに関するメモ** null で終わる文字列を使用してください。  null で終わる文字列はターゲット バッファーのサイズを超えないようにしてください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
 `dest` か `src` が `NULL` の場合、関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター エラーを生成します。  エラーが処理されたとき、関数は `EINVAL` を返し、`EINVAL` に `errno` を設定します。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsncat`|[strncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|`_mbsnbcat`|[wcsncat](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|  
|`_tcsncat_l`|`_strncat_l`|`_mbsnbcat_l`|`_wcsncat_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbsnbcat`|\<mbstring.h\>|  
|`_mbsnbcat_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcmp、\_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_strncnt、\_wcsncnt、\_mbsnbcnt、\_mbsnbcnt\_l、\_mbsnccnt、\_mbsnccnt\_l](../Topic/_strncnt,%20_wcsncnt,%20_mbsnbcnt,%20_mbsnbcnt_l,%20_mbsnccnt,%20_mbsnccnt_l.md)   
 [\_mbsnbcpy、\_mbsnbcpy\_l](../Topic/_mbsnbcpy,%20_mbsnbcpy_l.md)   
 [\_mbsnbicmp、\_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [\_mbsnbset、\_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [strncat、\_strncat\_l、wcsncat、\_wcsncat\_l、\_mbsncat、\_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [\_mbsnbcat\_s、\_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md)