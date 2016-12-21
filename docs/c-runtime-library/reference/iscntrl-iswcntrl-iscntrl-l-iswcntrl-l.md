---
title: "iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l | Microsoft Docs"
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
  - "iscntrl"
  - "_iswcntrl_l"
  - "_iscntrl_l"
  - "iswcntrl"
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
  - "_istcntrl_l"
  - "_iswcntrl_l"
  - "iswcntrl"
  - "_iscntrl_l"
  - "iscntrl"
  - "_istcntrl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_iscntrl_l 関数"
  - "_istcntrl 関数"
  - "_istcntrl_l 関数"
  - "_iswcntrl_l 関数"
  - "iscntrl 関数"
  - "istcntrl 関数"
  - "iswcntrl 関数"
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iscntrl、iswcntrl、_iscntrl_l、_iswcntrl_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数が制御文字を表すかどうかを判定します。  
  
## 構文  
  
```  
int iscntrl(   
   int c   
);  
int iswcntrl(   
   wint_t c   
);  
int _iscntrl_l(   
   int c,  
   _locale_t locale  
);  
int _iswcntrl_l(   
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 テストする整数  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの各ルーチンでは、`c` が制御文字の特殊表現の場合は 0 以外の値を返します。  `c` が制御文字 \(0x09 ～ 0x0D または 0x20\) の場合、`iscntrl` は 0 以外の値を返します。  `c` が制御ワイド文字の場合、`iswcntrl` は 0 以外の値を返します。  これらの各ルーチンは、`c` がテスト条件を満たしていない場合は 0 を返します。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `iscntrl` と `_iscntrl_l` の動作は、`c` が EOF ではなく、かつ、0 ～ 0xFF の範囲でない場合は未定義です。  CRT デバッグ ライブラリを使用し、`c` がこれらの値のうちのいずれかの値でない場合は、アサーションが発生します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_istcntrl`|`iscntrl`|`iscntrl`|`iswcntrl`|  
|`_istcntrl_l`|`_iscntrl_l`|`_iscntrl_l`|`_iswcntrl_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`iscntrl`|\<ctype.h\>|  
|`iswcntrl`|\<ctype.h\> または \<wchar.h\>|  
|`_iscntrl_l`|\<ctype.h\>|  
|`_iswcntrl_l`|\<ctype.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Char::IsControl](https://msdn.microsoft.com/en-us/library/system.char.iscontrol.aspx)  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)