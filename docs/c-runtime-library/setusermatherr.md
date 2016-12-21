---
title: "__setusermatherr | Microsoft Docs"
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
  - "__setusermatherr"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__setusermatherr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__setusermatherr"
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __setusermatherr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーが指定した rountine を [\_matherr](../c-runtime-library/reference/matherr.md) ルーチンの代わりに、数値演算エラーを処理することを指定します。  
  
## 構文  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
  
```  
  
#### パラメーター  
 `pf`  
 ユーザーによって指定された `_matherr` の実装へのポインター。  
  
 `pf` パラメーターの型は、`typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`として宣言されます。  
  
## 解説  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_\_setusermatherr|matherr.c|