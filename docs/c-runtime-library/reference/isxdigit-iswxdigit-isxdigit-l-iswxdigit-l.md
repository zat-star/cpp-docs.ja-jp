---
title: "isxdigit、iswxdigit、_isxdigit_l、_iswxdigit_l | Microsoft Docs"
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
  - "_iswxdigit_l"
  - "iswxdigit"
  - "isxdigit"
  - "_isxdigit_l"
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
  - "iswxdigit"
  - "isxdigit"
  - "_istxdigit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_istxdigit 関数"
  - "_iswxdigit_l 関数"
  - "_isxdigit_l 関数"
  - "16 進文字"
  - "istxdigit 関数"
  - "iswxdigit 関数"
  - "iswxdigit_l 関数"
  - "isxdigit 関数"
  - "isxdigit_l 関数"
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isxdigit、iswxdigit、_isxdigit_l、_iswxdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数が 16 進数字の文字を表すかどうかを判断します。  
  
## 構文  
  
```  
int isxdigit(  
   int c   
);  
int iswxdigit(  
   wint_t c   
);  
int _isxdigit_l(  
   int c,  
   _locale_t locale  
);  
int _iswxdigit_l(  
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
 これらのルーチンでは、`c` が 16 進数字の特殊表現の場合は 0 以外の値を返します。  `isxdigit` は `c` が 16 進数字 \(A ～ F、a ～ f、または 0 ～ 9\) の場合 0 以外の値を返します。  `iswxdigit` は `c` が標準の 16 進数字に対応するワイド文字の場合、0 以外の値を返します。  これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
 "C" ロケールの場合、`iswxdigit` 関数は、Unicode の全角 16 進数字はサポートしません。  
  
 これらの関数のうち `_l` サフィックスが付いているバージョンは、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `isxdigit` と `_isxdigit_l` の動作は、`c` が EOF ではなく、かつ、0 ～ 0xFF の範囲でない場合は未定義です。  CRT デバッグ ライブラリを使用し、`c` がこれらの値のうちのいずれかの値でない場合は、アサーションが発生します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_istxdigit`|`isxdigit`|`isxdigit`|`iswxdigit`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`isxdigit`|\<ctype.h\>|  
|`iswxdigit`|\<ctype.h\> または \<wchar.h\>|  
|`_isxdigit_l`|\<ctype.h\>|  
|`_iswxdigit_l`|\<ctype.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Char::IsNumber](https://msdn.microsoft.com/en-us/library/system.char.isnumber.aspx)  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)