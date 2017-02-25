---
title: "_ismbbkprint、_ismbbkprint_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbkprint"
  - "_ismbbkprint_l"
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
  - "_ismbbkprint_l"
  - "ismbbkprint"
  - "_ismbbkprint"
  - "ismbbkprint_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbbkprint 関数"
  - "ismbbkprint_l 関数"
  - "ismbbkprint 関数"
  - "_ismbbkprint_l 関数"
ms.assetid: 8d1d3258-1e34-4365-81ed-97c95de25475
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _ismbbkprint、_ismbbkprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

特定のマルチバイト文字が区切り記号かどうかを判定します。  
  
## 構文  
  
```  
int _ismbbkprint(  
   unsigned int c   
);  
int _ismbbkprint_l(  
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
 `_ismbbkprint` は、整数 `c` が非 ASCII テキストまたは非 ASCII 区切り記号の場合は 0 以外の値を返し、それ以外の場合は 0 を返します。 たとえば、コード ページ 932 でのみ、`_ismbbkprint` はカタカナの英数字、またはカタカナの句読点 \(範囲: 0xA1 ～ 0xDF\) をテストします。`_ismbbkprint` は、ロケールに依存する文字設定に現在のロケールを使用します。`_ismbbkprint_l` は、代わりに渡されるロケールを使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ismbbkprint`|\<mbctype.h\>|  
|`_ismbbkprint_l`|\<mbctype.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)