---
title: "_fpclass _fpclassf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpclass"
  - "_fpclassf"
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
  - "fpclass"
  - "_fpclass"
  - "_fpclassf"
  - "math/_fpclass"
  - "float/_fpclass"
  - "math/_fpclassf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fpclass 関数"
  - "浮動小数点数、IEEE 表現"
  - "_fpclass 関数"
  - "_fpclassf 関数"
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _fpclass _fpclassf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

引数の浮動小数点の分類を示す値を返します。  
  
## 構文  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## 戻り値  
 `_fpclass` と `_fpclassf` 関数を引数の浮動小数点の分類を示す整数値を返す `x`します。 分類は、\< float.h \> で定義されている、次の値のいずれかのがあります。  
  
|値|説明|  
|-------|--------|  
|`_FPCLASS_SNAN`|シグナリング NaN|  
|`_FPCLASS_QNAN`|簡易な NaN|  
|`_FPCLASS_NINF`|負の無限大 \(– INF\)|  
|`_FPCLASS_NN`|負の値が 0 以外を正規化|  
|`_FPCLASS_ND`|負の値を非正規化|  
|`_FPCLASS_NZ`|負のゼロ \(– 0\)|  
|`_FPCLASS_PZ`|正の 0 \(\+0\)|  
|`_FPCLASS_PD`|正の非正規化|  
|`_FPCLASS_PN`|正規化されたゼロ以外の正|  
|`_FPCLASS_PINF`|正の無限大 \(\+ INF\)|  
  
## 解説  
 `_fpclass` と `_fpclassf` の関数は、Microsoft 固有の仕様です。 似ている [fpclassify](../../c-runtime-library/reference/fpclassify.md), が引数に関する詳細な情報を返します。`_fpclassf` 関数は、x64 用にコンパイルされるときに使用できるプラットフォームです。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fpclass`|\<float.h\>|  
  
 詳細の互換性と準拠については、次を参照してください。 [互換性](../../c-runtime-library/compatibility.md)します。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、\_isnan、\_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)