---
title: "fesetenv1 | Microsoft Docs"
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
  - "fesetenv"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fesetenv"
  - "fenv/fesetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fesetenv 関数"
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fesetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の浮動小数点環境を設定します。  
  
## 構文  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### パラメーター  
 `penv`  
 ポインター、 `fenv_t` オブジェクトとして含まれている浮動小数点環境設定への呼び出しによって [fegetenv](../Topic/fegetenv2.md) または [feholdexcept](../Topic/feholdexcept1.md)です。 既定のスタートアップの浮動小数点環境は、FE\_DFL\_ENV マクロを使用しても指定できます。  
  
## 戻り値  
 環境が正常に設定されている場合は、0 を返します。 それ以外の場合、0 以外の値を返します。  
  
## 解説  
 `fesetenv` 関数に格納されている値から現在の浮動小数点環境の設定、 `fenv_t` によって指されるオブジェクト `penv`します。 浮動ポイント環境は、一連の状態フラグと浮動小数点計算に影響するコントロールのモードです。 これには、丸めモードと浮動小数点例外用の状態フラグが含まれます。 場合 `penv` FE\_DFL\_ENV でがないか、有効なを指していない `fenv_t` オブジェクト、その後の動作は未定義です。  
  
 この関数を呼び出すと例外が内にあるステータスのフラグ設定、 `penv` オブジェクトが、それらの例外は発生しません。  
  
 この関数を使用するのには、浮動小数点の最適化を使用してアクセスを妨げる可能性のあるオフにする必要があります、 `#pragma fenv_access(on)` 呼び出しの前にディレクティブです。 詳細については、「[fenv\_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`fesetenv`|\<fenv.h\>|\<cfenv\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [分かって](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../Topic/fesetexceptflag2.md)