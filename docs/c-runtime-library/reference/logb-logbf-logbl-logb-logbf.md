---
title: "logb、logbf、logbl、_logb、_logbf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "logb"
  - "_logb"
  - "_logbl"
  - "logbf"
  - "logbl"
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
  - "logb"
  - "logbl"
  - "_logb"
  - "_logbf"
  - "logbf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_logb 関数"
  - "_logbf 関数"
  - "指数, 浮動小数点数"
  - "指数部と仮数部"
  - "浮動小数点関数"
  - "浮動小数点関数, 仮数と指数"
  - "logb 関数"
  - "logbf 関数"
  - "logbl 関数"
  - "仮数部, 浮動小数点変数"
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# logb、logbf、logbl、_logb、_logbf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点引数の指数の値を抽出します。  
  
## 構文  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### パラメーター  
 x  
 浮動小数点値。  
  
## 戻り値  
 `logb` は、符号付き整数が浮動小数点値として示すように `x` の公平な指数値を返します。  
  
## 解説  
 `logb` 関数は `x` が無限範囲で示されているかのように、浮動小数点引数 `x` の指数値を抽出します。  引数 `x` が非正規化されている場合でも、正規化されているかのように扱われます。  
  
 C\+\+ ではオーバーロードが可能であるため、`float` または `long double` の値を受け取って返す `logb` のオーバーロードを呼び出すことができます。  C プログラムでは、`logb` は常に `double` を受け取って返します。  
  
|入力|SEH の例外|Matherr 例外|  
|--------|-------------|----------------|  
|± QNAN、IND|なし。|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_logb`|\<float.h\>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)