---
title: "_ismbblead、_ismbblead_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbblead_l"
  - "_ismbblead"
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
  - "ismbblead_l"
  - "istlead"
  - "_ismbblead"
  - "_ismbblead_l"
  - "ismbblead"
  - "_istlead"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbblead_l 関数"
  - "ismbblead 関数"
  - "_ismbblead 関数"
  - "istlead 関数"
  - "ismbblead_l 関数"
  - "_istlead 関数"
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _ismbblead、_ismbblead_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字をテストして、その文字がマルチバイト文字の先行バイトかどうかを判定します。  
  
## 構文  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 テストする整数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 整数 `c` がマルチバイト文字の先行バイトの場合、0 以外の値を返します。  
  
## 解説  
 マルチバイト文字は、先行バイトとそれに続く後続バイトで構成されます。 先行バイトは、特定の文字セットの特定の範囲内にあるかどうかで識別されます。 たとえば、コード ページ 932 の場合のみ、先行バイトの範囲は 0x81 ～ 0x9F および 0xE0 ～ 0xFC です。  
  
 `_ismbblead` は、ロケールに依存する動作に現在のロケールを使用します。`_ismbblead_l` は、代わりに渡されるロケールを使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_istlead`|常に false を返します|`_ismbblead`|常に false を返します|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_ismbblead`|\<mbctype.h\> または \<mbstring.h\>|\<ctype.h\>\*、\<limits.h\>、\<stdlib.h\>|  
|`_ismbblead_l`|\<mbctype.h\> または \<mbstring.h\>|\<ctype.h\>\*、\<limits.h\>、\<stdlib.h\>|  
  
 \* テスト条件のマニフェスト定数の場合。  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)