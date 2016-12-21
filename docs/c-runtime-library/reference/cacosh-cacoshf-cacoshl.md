---
title: "cacosh、cacoshf、cacoshl | Microsoft Docs"
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
  - "cacosh"
  - "cacoshf"
  - "cacoshl"
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
  - "cacosh"
  - "cacoshf"
  - "cacoshl"
  - "complex/cacosh"
  - "complex/cacoshf"
  - "complex/cacoshl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "cacosh 関数"
  - "cacoshf 関数"
  - "cacoshl 関数"
ms.assetid: 83fd05eb-3587-4741-9be6-589a830a1703
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cacosh、cacoshf、cacoshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

分岐では実際の軸に沿って 1 より小さい値でカット複素数の逆ハイパーボリック コサインを取得します。 .  
  
## 構文  
  
```  
_Dcomplex cacosh(   
   _Dcomplex z   
);  
_Fcomplex cacosh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cacosh(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cacoshf(   
   _Fcomplex z   
);  
_Lcomplex cacoshl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 ラジアン単位の角度を表す複素数。  
  
## 戻り値  
 逆ハイパーボリック コサイン `z`, 、ラジアンにします。 結果は、unbounded と実際の軸に沿ったと虚数部の軸に沿った間隔 \[−iπ、\+ iπ\] で負でないです。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`cacosh` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは `cacosh` は、 `_Dcomplex` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`cacosh`、`cacoshf`、`cacoshl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh、catanhf、catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh、ctanhf、ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan、catanf、catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh、csinhf、csinhl](../Topic/csinh,%20csinhf,%20csinhl.md)   
 [casinh、casinhf、casinhl](../Topic/casinh,%20casinhf,%20casinhl.md)   
 [ccosh、ccoshf、ccoshl](../Topic/ccosh,%20ccoshf,%20ccoshl.md)   
 [cacos、cacosf、cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan、ctanf、ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin、csinf、csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin、casinf、casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos、ccosf、ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt、csqrtf、csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)