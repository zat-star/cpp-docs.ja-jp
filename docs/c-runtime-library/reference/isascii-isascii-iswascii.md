---
title: "isascii、_ _isascii、iswascii | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswascii"
  - "__isascii"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "iswascii"
  - "istascii"
  - "__isascii"
  - "_istascii"
  - "isascii"
  - "ctype/isascii"
  - "ctype/__isascii"
  - "corecrt_wctype/iswascii"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__isascii 関数"
  - "_isascii 関数"
  - "isascii 関数"
  - "_istascii 関数"
  - "istascii 関数"
  - "iswascii 関数"
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# isascii、_ _isascii、iswascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

特定の文字が ASCII 文字であるかどうかを判断します。  
  
## 構文  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### パラメーター  
 `c`  
 テストする整数。  
  
## 戻り値  
 これらのルーチンを返します。 0 以外の場合の各 `c` は ASCII 文字の特殊表現します。`__isascii` 0 以外の値を返します `c` ASCII 文字 \(範囲の 0x00 ~ 0x7F\)。`iswascii` 0 以外の値を返します `c` ASCII 文字のワイド文字表現です。 これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
## 解説  
 両方とも `__isascii` と `iswascii` プリプロセッサ マクロ \_CTYPE\_DISABLE\_MACROS が定義されていない場合、マクロとして実装されます。  
  
 旧バージョンとの互換性のため `isascii` をマクロとして実装された [\_ \_stdc \_ \_](../../preprocessor/predefined-macros.md) が定義されていないか 0; として定義されてそれ以外の場合に未定義です。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`isascii`, `__isascii`|C: \< ctype.h \><br /><br /> C\+\+ の場合: \< cctype \> または \< ctype.h \>|  
|`iswascii`|C: \< wctype.h \> \< ctype.h \> または \< wchar.h \><br /><br /> C\+\+ の場合: \< cwctype \> \< cctype \> \< wctype.h \> \< ctype.h \> または \< wchar.h \>|  
  
 `isascii`, 、`__isascii` と `iswascii` 関数は、Microsoft 固有の仕様です。 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)