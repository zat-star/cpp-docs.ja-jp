---
title: "_ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l | Microsoft Docs"
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
  - "_ismbclower"
  - "_ismbclower_l"
  - "_ismbcupper_l"
  - "_ismbcupper"
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
  - "_ismbcupper"
  - "_ismbclower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclower 関数"
  - "_ismbclower_l 関数"
  - "_ismbcupper 関数"
  - "_ismbcupper_l 関数"
  - "ismbclower 関数"
  - "ismbclower_l 関数"
  - "ismbcupper 関数"
  - "ismbcupper_l 関数"
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字が小文字または大文字であるかどうかをチェックします。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 テストする文字。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。  `c`が \=\<255 およびそこに `_ismbb` 対応するルーチン \(たとえば、`_ismbcalnum` は `_ismbbalnum`に相当します\) の場合、結果は `_ismbb` 対応するルーチンの戻り値です。  
  
## 解説  
 これらの各関数は特定の条件で特定のマルチバイト文字をテストします。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用するという点で異なります。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
|ルーチン|テスト条件|コード ページ 932 の例|  
|----------|-----------|--------------------|  
|`_ismbclower`|小文字の英字|`c` が ASCII 小文字の英字 \(0x61 \<\= `c`\<\= 0x7A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbclower_l`|小文字の英字|`c` が ASCII 小文字の英字 \(0x61 \<\= `c`\<\= 0x7A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcupper`|大文字の英字|`c` が ASCII 大文字の英字 \(0x41 \<\= `c`\<\= 00x5A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcupper_l`|大文字の英字|`c` が ASCII 大文字の英字 \(0x41 \<\= `c`\<\= 00x5A\) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbclower`|\<mbstring.h\>|  
|`_ismbclower_l`|\<mbstring.h\>|  
|`_ismbcupper`|\<mbstring.h\>|  
|`_ismbcupper_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
-   [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [\_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)