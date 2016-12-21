---
title: "_ismbbtrail、_ismbbtrail_l | Microsoft Docs"
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
  - "_ismbbtrail"
  - "_ismbbtrail_l"
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
  - "_ismbbtrail"
  - "ismbbtrail"
  - "_ismbbtrail_l"
  - "ismbbtrail_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ismbbtrail_l 関数"
  - "_ismbbtrail 関数"
  - "_ismbbtrail_l 関数"
  - "ismbbtrail 関数"
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbbtrail、_ismbbtrail_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイトがマルチバイト文字の後続バイトかどうかを判定します。  
  
## 構文  
  
```  
int _ismbbtrail(  
   unsigned int c   
);  
int _ismbbtrail_l(  
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
 整数 `c` がマルチバイト文字の 2 番目のバイトの場合、`_ismbbtrail` は 0 以外の値を返します。 たとえば、コード ページ 932 でのみ、有効な範囲は 0x40 – 0x7E、0x80 – 0xFC です。  
  
## 解説  
 `_ismbbtrail` は、ロケールに依存する動作に現在のロケールを使用します。`_ismbbtrail_l` は、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_ismbbtrail`|\<mbctype.h\> または \<mbstring.h\>|\<ctype.h\>\*、\<limits.h\>、\<stdlib.h\>|  
|`_ismbbtrail_l`|\<mbctype.h\> または \<mbstring.h\>|\<ctype.h\>\*、\<limits.h\>、\<stdlib.h\>|  
  
 \* テスト条件のマニフェスト定数の場合。  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)