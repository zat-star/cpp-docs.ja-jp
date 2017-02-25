---
title: "fabs、fabsf、fabsl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fabsf"
  - "fabs"
  - "fabsl"
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
  - "fabs"
  - "fabsf"
  - "fabsl"
  - "math\fabs"
  - "math\fabsf"
  - "math\fabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "絶対値"
  - "fabsf 関数"
  - "計算 (絶対値を)"
  - "fabs 関数"
  - "fabsl 関数"
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fabs、fabsf、fabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点引数の絶対値を計算します。  
  
## 構文  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### パラメーター  
 `x`  
 浮動小数点値。  
  
## 戻り値  
 `fabs` 関数は引数の絶対値を返す `x`します。 エラーの戻り値はありません。  
  
|入力|SEH 例外|Matherr 例外|  
|--------|------------|----------------|  
|± QNAN、IND|none|\_DOMAIN|  
  
## 解説  
 C\+\+ では、オーバー ロードのオーバー ロードを呼び出すことができますので `fabs` \< cmath \> ヘッダーを含める場合。 C プログラムでは、`fabs` は常に double を受け取って返します。  
  
## 必要条件  
  
|関数|必須の C ヘッダー|必要な C\+\+ ヘッダー|  
|--------|----------------|--------------------|  
|`fabs`、`fabsf`、`fabsl`|\<math.h\>|\< cmath \> または \< math.h \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md) 関数の例を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [abs、labs、llabs、\_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../Topic/_cabs.md)   
 [labs、llabs](../../misc/labs-llabs.md)