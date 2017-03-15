---
title: "数値演算定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USE_MATH_DEFINES 定数"
  - "定数, 数値演算"
  - "M_1_PI 定数"
  - "M_2_PI 定数"
  - "M_2_SQRTPI 定数"
  - "M_E 定数"
  - "M_LN10 定数"
  - "M_LN2 定数"
  - "M_LOG10E 定数"
  - "M_LOG2E 定数"
  - "M_PI 定数"
  - "M_PI_2 定数"
  - "M_PI_4 定数"
  - "M_SQRT1_2 定数"
  - "M_SQRT2 定数"
  - "数値演算定数"
  - "USE_MATH_DEFINES 定数"
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 数値演算定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## 解説  
 指定された式の値として、次のシンボルが定義されています。  
  
|シンボル|式|値|  
|----------|-------|-------|  
|M\_E|e|2.71828182845904523536|  
|M\_LOG2E|log2\(e\)|1.44269504088896340736|  
|M\_LOG10E|log10\(e\)|0.434294481903251827651|  
|M\_LN2|ln\(2\)|0.693147180559945309417|  
|M\_LN10|ln\(10\)|2.30258509299404568402|  
|M\_PI|pi|3.14159265358979323846|  
|M\_PI\_2|pi\/2|1.57079632679489661923|  
|M\_PI\_4|pi\/4|0.785398163397448309616|  
|M\_1\_PI|1\/pi|0.318309886183790671538|  
|M\_2\_PI|2\/pi|0.636619772367581343076|  
|M\_2\_SQRTPI|2\/sqrt\(pi\)|1.12837916709551257390|  
|M\_SQRT2|sqrt\(2\)|1.41421356237309504880|  
|M\_SQRT1\_2|1\/sqrt\(2\)|0.707106781186547524401|  
  
 数値演算定数は標準 C\/C\+\+ では定義されていません。  これらの定数を使用するには、最初に `_USE_MATH_DEFINES` を定義してから、cmath または math.h をインクルードする必要があります。  
  
 リリース モードでプロジェクトをビルドする場合、ファイル ATLComTime.h に math.h が含まれます。  ATLComTime.h をインクルードしているプロジェクトで 1 つ以上の数値演算定数を使用する場合は、ATLComTime.h をインクルードする前に `_USE_MATH_DEFINES` を定義する必要があります。  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)