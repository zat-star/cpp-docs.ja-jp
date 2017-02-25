---
title: "数値演算エラー定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_PLOSS"
  - "_UNDERFLOW"
  - "_TLOSS"
  - "_SING"
  - "_DOMAIN"
  - "_OVERFLOW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_DOMAIN 定数"
  - "_OVERFLOW 定数"
  - "_PLOSS 定数"
  - "_SING 定数"
  - "_TLOSS 定数"
  - "_UNDERFLOW 定数"
  - "DOMAIN 定数"
  - "数値演算エラー定数"
  - "OVERFLOW 定数"
  - "PLOSS 定数"
  - "SING 定数"
  - "TLOSS 定数"
  - "UNDERFLOW 定数"
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 数値演算エラー定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <math.h>  
  
```  
  
## 解説  
 ランタイム ライブラリの数値演算ルーチンは、数値演算エラーの定数を生成できます。  
  
 次のように記述されているこれらのエラーは MATH.H で定義されている例外の種類に数値演算エラーが発生したときに対応し、`_matherr` 関数によって返されます。  
  
|定数|説明|  
|--------|--------|  
|`_DOMAIN`|使用できる引数は、関数の外部ドメインです。|  
|`_OVERFLOW`|結果は関数の戻り値の型で表すには大きすぎるため、|  
|`_PLOSS`|重要度の部分的な損失が発生しました。|  
|`_SING`|引数:不適切 関数の引数に無効な値があります。\(たとえば、0 以外の値を必要とする値 0 が機能するために渡されます。|  
|`_TLOSS`|重要度に障害が発生しました。|  
|`_UNDERFLOW`|結果を表すことが小さすぎる。|  
  
## 参照  
 [\_matherr](../c-runtime-library/reference/matherr.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)