---
title: "__max | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__max"
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
apitype: "DLLExport"
f1_keywords: 
  - "max"
  - "__max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__max マクロ"
  - "max マクロ"
  - "最大値マクロ"
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __max
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値 2 の方の値を返します。  
  
## 構文  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### パラメーター  
 `type`  
 数値データ型。  
  
 `a, b`  
 比較される数値型の値。  
  
## 戻り値  
 `__max` は 引数の方の値を返します。  
  
## 解説  
 `__max` マクロは 2 個の値を比較し、大きなものという値を返します。  引数は、数値データ型または署名されて符号なしです。  引数と戻り値は、同じデータ型である必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`__max`|\<stdlib.h\>|  
  
## 使用例  
 詳細については、[\_\_min](../../c-runtime-library/reference/min.md)"の例を参照します。  
  
## 同等の .NET Framework 関数  
 [System::Math::Max](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_\_min](../../c-runtime-library/reference/min.md)