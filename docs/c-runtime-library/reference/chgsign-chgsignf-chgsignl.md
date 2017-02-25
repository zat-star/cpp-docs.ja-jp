---
title: "_chgsign、_chgsignf、_chgsignl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chgsignl"
  - "_chgsign"
  - "_chgsignf"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_chgsignf"
  - "chgsign"
  - "_chgsignl"
  - "_chgsign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chgsign 関数"
  - "_chgsignf 関数"
  - "_chgsignl 関数"
  - "chgsign 関数"
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _chgsign、_chgsignf、_chgsignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点引数の符号を反転させます。  
  
## 構文  
  
```  
double _chgsign(   
   double x   
);  
float _chgsignf(  
   float x   
);  
long double _chgsignl(   
   long double x   
);  
```  
  
#### パラメーター  
 `x`  
 変更する浮動小数点値。  
  
## 戻り値  
 `_chgsign` 関数は、浮動小数点引数 `x` と等しく、符号を反転した値を返します。  エラーの戻り値はありません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_chgsign`|\<float.h\>|  
|`_chgsignf`, `_chgsignl`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [fabs、fabsf、fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [copysign、copysignf、copysignl、\_copysign、\_copysignf、\_copysignl](../../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)