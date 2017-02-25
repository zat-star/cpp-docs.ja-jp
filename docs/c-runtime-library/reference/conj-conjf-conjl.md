---
title: "conj、conjf、conjl | Microsoft Docs"
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
  - "conj"
  - "conjf"
  - "conjl"
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
  - "conj"
  - "conjf"
  - "conjl"
  - "complex/conj"
  - "complex/conjf"
  - "complex/conjl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conj 関数"
  - "conjf 関数"
  - "conjl 関数"
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# conj、conjf、conjl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

複素数の複素数の共役を取得します。  
  
## 構文  
  
```  
_Dcomplex conj(   
   _Dcomplex z   
);  
_Fcomplex conj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex conj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex conjf(   
   _Fcomplex z   
);  
_Lcomplex conjl(   
   _Lcomplex z   
);  
```  
  
#### パラメーター  
 `z`  
 複素数。  
  
## 戻り値  
 複素数の共役 `z`します。  結果がある同じ実数部と虚数部として `z`, 、逆の符号です。  
  
## 解説  
 C\+\+ ではオーバーロードが可能であるため、`conj` および `_Fcomplex` の値を受け取って返す `_Lcomplex` のオーバーロードを呼び出すことができます。 C プログラムでは `conj` は、 `_Dcomplex` 値。  
  
## 必要条件  
  
|ルーチン|C ヘッダー|C\+\+ ヘッダー|  
|----------|------------|----------------|  
|`conj`、`conjf`、`conjl`|\<complex.h\>|\< ccomplex \>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm、normf、norml](../Topic/norm,%20normf,%20norml1.md)   
 [creal、crealf、creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj、cprojf、cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [cimag、cimagf、cimagl](../Topic/cimag,%20cimagf,%20cimagl.md)   
 [carg、cargf、cargl](../Topic/carg,%20cargf,%20cargl.md)   
 [cab ファイル、cabsf、cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)