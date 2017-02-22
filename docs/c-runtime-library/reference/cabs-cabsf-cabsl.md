---
title: "cab ファイル、cabsf、cabsl | Microsoft Docs"
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
  - "cabs"
  - "cabsf"
  - "cabsl"
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
  - "cabs"
  - "cabsf"
  - "cabsl"
  - "complex/cabs"
  - "complex/cabsf"
  - "complex/cabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cabs 関数"
  - "cabsf 関数"
  - "cabsl 関数"
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# cab ファイル、cabsf、cabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

複素数の絶対値を取得します。  
  
## 構文  
  
```  
double cabs(   
   _Dcomplex z   
);  
float cabs(   
   _Fcomplex z   
);  // C++ only  
long double cabs(   
   _Lcomplex z   
);  // C++ only  
float cabsf(   
   _Fcomplex z   
);  
long double cabsl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 複素数。  
  
## 戻り値  
 絶対値 `z`します。  
  
## 解説  
 オーバー ロードを呼び出すことができますので、C ではオーバー ロード、 `cabs` を受け取る `_Fcomplex` または `_Lcomplex` 値、および戻り値 `float` または `long double` 値。 C プログラムでは `cabs` は常に、 `_Dcomplex` 値を返す、 `double` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`cabs`、`cabsf`、`cabsl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../Topic/norm,%20normf,%20norml1.md)   
 [creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj、conjf、conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag、cimagf、cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg、cargf、cargl](../Topic/carg,%20cargf,%20cargl.md)