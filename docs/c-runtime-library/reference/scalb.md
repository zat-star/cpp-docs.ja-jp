---
title: "_scalb | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_scalb"
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
  - "scalb"
  - "_scalb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_scalb 関数"
  - "指数演算"
  - "scalb 関数"
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _scalb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2.の累乗で引数をスケーリングします。  
  
## 構文  
  
```  
double _scalb(  
   double x,  
   long exp   
);  
```  
  
#### パラメーター  
 `x`  
 倍精度、浮動小数点値。  
  
 `exp`  
 長整数の指数。  
  
## 戻り値  
 正常終了した場合は指数の値を返します。  オーバーフロー \(`x`の符号に応じて\)、`_scalb` は \+\/– `HUGE_VAL`;を返します `errno` の変数は `ERANGE`に設定されます。  
  
 これにより、他のリターン コードに関する詳細については、「[" \_doserrno、errno、\_sys\_errlist、および\_sys\_nerr "](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_scalb` 関数は `x *` 2exp の値を計算します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_scalb`|\<float.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)