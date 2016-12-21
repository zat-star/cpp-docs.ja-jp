---
title: "isspace、iswspace、_isspace_l、_iswspace_l | Microsoft Docs"
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
  - "iswspace"
  - "_isspace_l"
  - "_iswspace_l"
  - "isspace"
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
  - "iswspace"
  - "_istspace"
  - "isspace"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isspace_l 関数"
  - "_istspace 関数"
  - "_iswspace_l 関数"
  - "isspace 関数"
  - "isspace_l 関数"
  - "istspace 関数"
  - "iswspace 関数"
  - "iswspace_l 関数"
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isspace、iswspace、_isspace_l、_iswspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数が空白文字を表すかどうかを決定します。  
  
## 構文  
  
```  
int isspace(  
   int c   
);  
int iswspace(  
   wint_t c   
);  
int _isspace_l(  
   int c,  
   _locale_t locale  
);  
int _iswspace_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 テストする整数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらのルーチンでは、`c` が空白文字の特殊表現の場合は 0 以外の値を返します。  `isspace` は `c` が空白文字 \(0x09 – 0x0D または 0x20\) の場合、0 以外の値を返します。  `isspace` 関数のテスト条件の結果は、ロケールの `LC_CTYPE` カテゴリの設定に依存します。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこれらの関数のバージョンでは、ロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `iswspace` は `c` が標準の空白文字に対応するワイド文字の場合、0 以外の値を返します。  
  
 `isspace` と `_isspace_l` の動作は、`c` が EOF ではなく、かつ、0 ～ 0xFF の範囲でない場合は未定義です。  CRT デバッグ ライブラリを使用し、`c` がこれらの値のうちのいずれかの値でない場合は、アサーションが発生します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|**\_** `istspace`|`isspace`|[\_ismbcspace](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswspace`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`isspace`|\<ctype.h\>|  
|`iswspace`|\<ctype.h\> または \<wchar.h\>|  
|`_isspace_l`|\<ctype.h\>|  
|`_iswspace_l`|\<ctype.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)