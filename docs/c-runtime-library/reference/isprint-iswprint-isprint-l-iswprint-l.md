---
title: "isprint、iswprint、_isprint_l、_iswprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswprint"
  - "isprint"
  - "_isprint_l"
  - "_iswprint_l"
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
  - "iswprint"
  - "_istprint"
  - "isprint"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isprint_l 関数"
  - "_istprint 関数"
  - "_iswprint_l 関数"
  - "isprint 関数"
  - "isprint_l 関数"
  - "istprint 関数"
  - "iswprint 関数"
  - "iswprint_l 関数"
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isprint、iswprint、_isprint_l、_iswprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数が印刷可能な文字を表すかどうかを決定します。  
  
## 構文  
  
```  
int isprint(  
   int c   
);  
int iswprint(  
   wint_t c   
);  
int _isprint_l(  
   int c,  
   _locale_t locale  
);  
int _iswprint_l(  
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
 これらのルーチンでは、`c` が印刷可能な文字の特殊表現の場合は 0 以外の値を返します。  `isprint` は、`c` が印刷可能な文字 \(空白文字 \(0x20 – 0x7E\) を含む\) である場合、0 以外の値を返します。  `iswprint` は、`c` が印刷可能なワイド文字 \(空白ワイド文字を含む\) である場合、0 以外の値を返します。  これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
 これらの関数のテスト条件の結果は、ロケールの `LC_CTYPE` カテゴリの設定に依存します。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこれらの関数のバージョンでは、ロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `isprint` と `_isprint_l` の動作は、`c` が EOF ではなく、かつ、0 ～ 0xFF の範囲でない場合は未定義です。  CRT デバッグ ライブラリを使用し、`c` がこれらの値のうちのいずれかの値でない場合は、アサーションが発生します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_Unicode が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|**\_** `istprint`|`isprint`|[\_ismbcprint](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswprint`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`isprint`|\<ctype.h\>|  
|`iswprint`|\<ctype.h\> または \<wchar.h\>|  
|`_isprint_l`|\<ctype.h\>|  
|`_iswprint_l`|\<ctype.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)