---
title: "csqrt、csqrtf、csqrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "csqrt"
  - "csqrtf"
  - "csqrtl"
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
  - "csqrt"
  - "csqrtf"
  - "csqrtl"
  - "complex/csqrt"
  - "complex/csqrtf"
  - "complex/csqrtl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "csqrt 関数"
  - "csqrtf 関数"
  - "csqrtl 関数"
ms.assetid: b65f086b-0f55-4622-a7a3-4e79d9c9c05c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# csqrt、csqrtf、csqrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

負の値の実際の軸に沿って切り込み分岐では、複素数の平方根を取得します。  
  
## 構文  
  
```  
_Dcomplex csqrt(   
   _Dcomplex z   
);  
_Fcomplex csqrt(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex csqrt(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex csqrtf(   
   _Fcomplex z   
);  
_Lcomplex csqrtl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 複素数。  
  
## 戻り値  
 平方根 `z`します。 右側の半分平面になります。  
  
|入力|SEH 例外|`_matherr` 例外|  
|--------|------------|-------------------|  
|± QNAN、IND|none|\_DOMAIN|  
|\- ∞|none|\_DOMAIN|  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`csqrt` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは `csqrt` は、 `_Dcomplex` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`csqrt`、`csqrtf`、`csqrtl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh、catanhf、catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
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