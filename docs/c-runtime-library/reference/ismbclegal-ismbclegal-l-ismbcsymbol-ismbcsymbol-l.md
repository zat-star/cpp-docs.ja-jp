---
title: "_ismbclegal、_ismbclegal_l、_ismbcsymbol、_ismbcsymbol_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "_ismbcsymbol"
  - "_ismbcsymbol_l"
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
  - "ismbcsymbol_l"
  - "_ismbcsymbol_l"
  - "_ismbcsymbol"
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "ismbclegal_l"
  - "ismbcsymbol"
  - "ismbclegal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbclegal 関数"
  - "_ismbclegal_l 関数"
  - "_ismbcsymbol 関数"
  - "_ismbcsymbol_l 関数"
  - "_istlegal 関数"
  - "_istlegal_l 関数"
  - "ismbclegal 関数"
  - "ismbclegal_l 関数"
  - "ismbcsymbol 関数"
  - "ismbcsymbol_l 関数"
  - "istlegal 関数"
  - "istlegal_l 関数"
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _ismbclegal、_ismbclegal_l、_ismbcsymbol、_ismbcsymbol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字が有効な文字または記号かどうかをチェックします。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
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
|`_ismbclegal`|有効なマルチバイト|`c` の最初のバイトが 0x81 ～ 0x9F または 0xE0 ～ 0xFC の範囲内にあり、2 番目のバイトが 0x40 ～ 0x7E または 0x80 ～ FC の範囲内にある場合にのみ、0 以外の値を返します。|  
|`_ismbcsymbol`|マルチバイトの記号|0x8141\<\=`c`\<\=0x81AC の場合にのみ、0 以外の値を返します。|  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_istlegal`|常に false を返します|`_ismbclegal`|常に false を返します。|  
|`_istlegal_l`|常に false を返します|`_ismbclegal_l`|常に false を返します。|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h\>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [\_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)