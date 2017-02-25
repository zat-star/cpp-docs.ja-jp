---
title: "ceil、ceilf、ceill | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ceilf"
  - "ceil"
  - "ceill"
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
  - "ceil"
  - "ceilf"
  - "ceill"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "計算 (切り上げ値を)"
  - "ceil 関数"
  - "ceilf 関数"
  - "ceill 関数"
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ceil、ceilf、ceill
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値の切り上げを計算します。  
  
## 構文  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 `ceil` 関数は `x` 以上の最も小さい整数を表す浮動小数点値を返します。  エラーの戻り値はありません。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|なし|`_DOMAIN`|  
  
 `ceil` には、ストリーミング SIMD 拡張機能 \(SSE2\) を使用して実装されています。  SSE2 実装の使い方の詳細および制約については、「[\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md)」を参照してください。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`ceil` のオーバーロードを呼び出すことができます。  C プログラムでは、`ceil` は常に double を受け取って返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[floor](../../c-runtime-library/reference/floor-floorf-floorl.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Math::Ceiling](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [floor、floorf、floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod、fmodf](../Topic/fmod,%20fmodf.md)   
 [round、roundf、roundl](../../c-runtime-library/reference/round-roundf-roundl.md)