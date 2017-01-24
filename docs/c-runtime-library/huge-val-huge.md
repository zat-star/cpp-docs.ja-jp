---
title: "HUGE_VAL, _HUGE | Microsoft Docs"
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
  - "_HUGE"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_HUGE"
  - "HUGE_VAL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HUGE 定数"
  - "HUGE_VAL 定数"
  - "double 型の値"
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# HUGE_VAL, _HUGE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <math.h>  
  
```  
  
## 解説  
 `HUGE_VAL` は 最大の表現できる double 値です。  この値は、多くの実行時の数値演算関数でエラーが発生した場合に返されます。  関数の場合、–`HUGE_VAL` が返されます。  `HUGE_VAL` は `_HUGE`、ランタイム数値演算関数 return `HUGE_VAL`として定義されます。  、一貫性のコードで `HUGE_VAL` を使用する必要があります。  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)