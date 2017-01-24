---
title: "_finite、_finitef | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_finite"
  - "_finitef"
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
  - "finite"
  - "_finite"
  - "_finitef"
  - "math/_finite"
  - "math/_finitef"
  - "float/_finite"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "finite 関数"
  - "_finite 関数"
  - "_finitef 関数"
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _finite、_finitef
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点値が有限かどうかを決定します。  
  
## 構文  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## 戻り値  
 `_finite` と `_finitef` は、引数 *x* が有限 \(つまり、INF \< `x` \< \+INF\) の場合、0 以外の値を返します。 引数が無限または NAN の場合は、0 を返します。  
  
## 解説  
 `_finite` と `_finitef` の関数は、Microsoft 固有の仕様です。`_finitef` 関数は、使用可能な場合では、プラットフォームを x86、ARM、または ARM64 用にコンパイルはのみです。  
  
## 必要条件  
  
|関数|必須ヘッダー \(C\)|必須ヘッダー \(C\+\+\)|  
|--------|------------------|----------------------|  
|`_finite`|\<float.h\> または \<math.h\>|\<float.h\>、\<math.h\>、\<cfloat\>、\<cmath\>|  
|`_finitef`|\<math.h\>|\<math.h\> または \<cmath\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、\_isnan、\_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [\_fpclass \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)