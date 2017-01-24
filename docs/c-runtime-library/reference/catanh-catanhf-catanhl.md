---
title: "catanh、catanhf、catanhl | Microsoft Docs"
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
  - "catanh"
  - "catanhf"
  - "catanhl"
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
  - "catanh"
  - "catanhf"
  - "catanhl"
  - "complex/catanh"
  - "complex/catanhf"
  - "complex/catanhl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "catanh 関数"
  - "catanhf 関数"
  - "catanhl 関数"
ms.assetid: 1b6021cb-647a-41b4-9d7f-919cc8b57b86
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# catanh、catanhf、catanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

複素数 cut、間隔以外での逆ハイパーボリック タンジェントを取得 \[− 1; \+1\] 実際の軸に沿ったします。  
  
## 構文  
  
```  
_Dcomplex catanh(   
   _Dcomplex z   
);  
_Fcomplex catanh(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex catanh(   
   _Lcomplex z   
);  //  C++ only  
_Fcomplex catanhf(   
   _Fcomplex z   
);  
_Lcomplex catanhl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 ラジアン単位の角度を表す複素数。  
  
## 戻り値  
 双曲線逆正接 `z`, 、ラジアンにします。 実際の軸に沿ったと虚数部の軸に沿った間隔 \[−iπ\/2; \+ iπ\/2\] に制限されます。 ドメイン エラーが発生 `z` が \[\-1, \+1\] 間隔の範囲外です。 極エラーが発生 `z` が\-1 または \+1 です。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`catanh` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは `catanh` は、 `_Dcomplex` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`catanh`、`catanhf`、`catanhl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [ctanh、ctanhf、ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan、catanf、catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh、csinhf、csinhl](../Topic/csinh,%20csinhf,%20csinhl.md)   
 [casinh、casinhf、casinhl](../Topic/casinh,%20casinhf,%20casinhl.md)   
 [ccosh、ccoshf、ccoshl](../Topic/ccosh,%20ccoshf,%20ccoshl.md)   
 [cacosh、cacoshf、cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos、cacosf、cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan、ctanf、ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin、csinf、csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin、casinf、casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos、ccosf、ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt、csqrtf、csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)