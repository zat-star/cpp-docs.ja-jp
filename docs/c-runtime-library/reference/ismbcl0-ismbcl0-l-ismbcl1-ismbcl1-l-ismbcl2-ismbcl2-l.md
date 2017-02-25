---
title: "_ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbcl2"
  - "_ismbcl1"
  - "_ismbcl0"
  - "_ismbcl2_l"
  - "_ismbcl1_l"
  - "_ismbcl0_l"
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
  - "ismbcl0"
  - "_ismbcl1_l"
  - "_ismbcl0"
  - "ismbcl1"
  - "ismbcl0_l"
  - "_ismbcl2_l"
  - "ismbcl2"
  - "ismbcl1_l"
  - "_ismbcl1"
  - "_ismbcl0_l"
  - "_ismbcl2"
  - "ismbcl2_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbcl0 関数"
  - "_ismbcl0_l 関数"
  - "_ismbcl1 関数"
  - "_ismbcl1_l 関数"
  - "_ismbcl2 関数"
  - "_ismbcl2_l 関数"
  - "ismbcl0 関数"
  - "ismbcl0_l 関数"
  - "ismbcl1 関数"
  - "ismbcl1_l 関数"
  - "ismbcl2 関数"
  - "ismbcl2_l 関数"
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のロケールまたは指定された LC\_CTYPE 変換状態カテゴリを使用する、コード ページ 932 固有の関数。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
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
 これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。  `c` が \= \<255 およびそこに `_ismbb` 対応するルーチン \(たとえば、`_ismbcalnum` は `_ismbbalnum`に相当します\) の場合、結果は `_ismbb` 対応するルーチンの戻り値です。  
  
## 解説  
 これらの各関数は特定の条件で特定のマルチバイト文字をテストします。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
|ルーチン|テスト条件 \(コード ページ 932 のみ\)|  
|----------|------------------------------|  
|`_ismbcl0`|JIS の非漢字: 0x8140\=\<`c`\<\=0x889E。|  
|`_ismbcl0_l`|JIS の非漢字: 0x8140\=\<`c`\<\=0x889E。|  
|`_ismbcl1`|JIS のレベル 1: 0x889F\=\<`c`\<\=0x9872。|  
|`_ismbcl1_l`|JIS のレベル 1: 0x889F\=\<`c`\<\=0x9872。|  
|`_ismbcl2`|JIS のレベル 2: 0x989F\=\<`c`\<\=0xEAA4。|  
|`_ismbcl2_l`|JIS のレベル 2: 0x989F\=\<`c`\<\=0xEAA4。|  
  
 関数は、指定された値 `c` が、上の表に記載のテスト条件に一致するかどうかをチェックしますが、`c` が有効なマルチバイト文字かどうかはチェックしません。  下位バイトが範囲 0x00 – 0x3F、0x7F、または 0xFD – 0xFF にある場合、これらの関数は 0 以外の値を返し、文字がテスト条件を満たすことを示します。  マルチバイト文字が定義されているかどうかをテストするために [\_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) を使用します。  
  
 **コード ページ 932 固有情報終了**  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbcl0`|\<mbstring.h\>|  
|`_ismbcl0_l`|\<mbstring.h\>|  
|`_ismbcl1`|\<mbstring.h\>|  
|`_ismbcl1_l`|\<mbstring.h\>|  
|`_ismbcl2`|\<mbstring.h\>|  
|`_ismbcl2_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [\_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)