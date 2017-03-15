---
title: "creal、crealf、creall | Microsoft Docs"
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
  - "creal"
  - "crealf"
  - "creall"
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
  - "creal"
  - "crealf"
  - "creall"
  - "complex/creal"
  - "complex/crealf"
  - "complex/creall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "creal 関数"
  - "crealf 関数"
  - "creall 関数"
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# creal、crealf、creall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

複素数の実数部を取得します。  
  
## 構文  
  
```  
double creal(   
   _Dcomplex z   
);  
float creal(   
   _Fcomplex z   
);  // C++ only  
long double creal(   
   _Lcomplex z   
);  // C++ only  
float crealf(   
   _Fcomplex z   
);  
long double creall(   
  _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 複素数。  
  
## 戻り値  
 実数部 `z`します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `creal` を受け取る `_Fcomplex` または `_Lcomplex` 値、および戻り値 `float` または `long double` 値。 C プログラムでは `creal` は常に、 `_Dcomplex` 値を返す、 `double` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`creal`、`crealf`、`creall`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../Topic/norm,%20normf,%20norml1.md)   
 [cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag、cimagf、cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg、cargf、cargl](../Topic/carg,%20cargf,%20cargl.md)   
 [cab ファイル、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)