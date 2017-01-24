---
title: "clog、clogf、clogl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clog"
  - "clogf"
  - "clogl"
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
  - "clog"
  - "clogf"
  - "clogl"
  - "complex/clog"
  - "complex/clogf"
  - "complex/clogl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "clog 関数"
  - "clogf 関数"
  - "clogl 関数"
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# clog、clogf、clogl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

負の値の実際の軸に沿って切り込み分岐では、複素数の自然対数を取得します。  
  
## 構文  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 対数の底。  
  
## 戻り値  
 自然対数 `z`します。 実際の軸に沿ったと虚数部の軸に沿った間隔 \[−iπ、\+ iπ\] に制限されます。  
  
 戻り値は次のとおりです。  
  
|z パラメーター|戻り値|  
|--------------|---------|  
|正|Z の底 10 の対数|  
|0|\- ∞|  
|負|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`clog` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは `clog` は、 `_Dcomplex` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`clog`、`clogf`、`clogl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp、cexpf、cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow、cpowf、cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10、clog10f、clog10l](../Topic/clog10,%20clog10f,%20clog10l.md)