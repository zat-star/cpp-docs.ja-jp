---
title: "分かって | Microsoft Docs"
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
  - "fetegenv"
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
  - "fegetenv"
  - "fenv/fegetenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fetegenv 関数"
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 分かって
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定したオブジェクトの現在の浮動小数点環境を格納します。  
  
## 構文  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### パラメーター  
 `penv`  
 ポインター、 `fenv_t` 浮動小数点環境の現在の値を格納するオブジェクト。  
  
## 戻り値  
 浮動小数点環境が正常に保存されていた場合は 0 を返します。 `penv`します。 それ以外の場合、0 以外の値を返します。  
  
## 解説  
 `fegetenv` 関数によって指されるオブジェクトに現在の浮動小数点環境を格納する `penv`です。 浮動ポイント環境は、一連の状態フラグと浮動小数点計算に影響するコントロールのモードです。 これには、丸めの方向モードと浮動小数点例外用の状態フラグが含まれます。 場合 `penv` が有効なを指していません `fenv_t` オブジェクト、その後の動作は未定義です。  
  
 この関数を使用するのには、浮動小数点の最適化を使用してアクセスを妨げる可能性のあるオフにする必要があります、 `#pragma fenv_access(on)` 呼び出しの前にディレクティブです。 詳細については、「[fenv\_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## 必要条件  
  
|関数|C ヘッダー|C\+\+ ヘッダー|  
|--------|------------|----------------|  
|`fegetenv`|\<fenv.h\>|\<cfenv\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 参照  
 [関数リファレンス \(アルファベット順\)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)