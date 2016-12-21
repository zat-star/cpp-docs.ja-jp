---
title: "浮動小数点定数の制限 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "定数, 浮動小数点"
  - "FLOAT.H ヘッダー ファイル"
  - "浮動小数点定数, 制限"
  - "浮動小数点数, 浮動小数点の制限"
  - "制限, 浮動小数点定数"
  - "範囲, 浮動小数点定数"
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 浮動小数点定数の制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 浮動小数点定数の値に関する制限を次の表に示します。  ヘッダー ファイル FLOAT.H にこの情報が含まれています。  
  
### 浮動小数点定数の制限  
  
|定数|説明|値|  
|--------|--------|-------|  
|**FLT\_DIGDBL\_DIGLDBL\_DIG**|*q* 桁の浮動小数点数を、精度を失わずに丸めて浮動小数点表現にしたり、戻したりできる桁数 *q*。|6 15 15|  
|**FLT\_EPSILONDBL\_EPSILONLDBL\_EPSILON**|*x* \+ 1.0 が 1.0 に等しくならないような最小の正数 *x*。|1.192092896e–07F 2.2204460492503131e–016 2.2204460492503131e–016|  
|**FLT\_GUARD**||0|  
|**FLT\_MANT\_DIGDBL\_MANT\_DIGLDBL\_MANT\_DIG**|浮動小数点の有効桁で **FLT\_RADIX** により指定された基数の桁数。  基数は 2 です。したがって、これらの値はビットを指定します。|24 53 53|  
|**FLT\_MAXDBL\_MAXLDBL\_MAX**|表現可能な最大浮動小数点数。|3.402823466e\+38F 1.7976931348623158e\+308 1.7976931348623158e\+308|  
|**FLT\_MAX\_10\_EXPDBL\_MAX\_10\_EXPLDBL\_MAX\_10\_EXP**|10 をその数値分累乗した結果が表現可能な浮動小数点数となる最大の整数。|38 308 308|  
|**FLT\_MAX\_EXPDBL\_MAX\_EXPLDBL\_MAX\_EXP**|**FLT\_RADIX** をその数値分累乗した結果が表現可能な浮動小数点数となる最大の整数。|128 1024 1024|  
|**FLT\_MINDBL\_MINLDBL\_MIN**|正の最小数。|1.175494351e–38F 2.2250738585072014e–308 2.2250738585072014e–308|  
|**FLT\_MIN\_10\_EXPDBL\_MIN\_10\_EXPLDBL\_MIN\_10\_EXP**|10 をその数値分累乗した結果が表現可能な浮動小数点数となる最小の負の整数。|–37<br /><br /> –307<br /><br /> –307|  
|**FLT\_MIN\_EXPDBL\_MIN\_EXPLDBL\_MIN\_EXP**|**FLT\_RADIX** をその数値分累乗した結果が表現可能な浮動小数点数となる最小の負の整数。|–125<br /><br /> –1021<br /><br /> –1021|  
|**FLT\_NORMALIZE**||0|  
|**FLT\_RADIX\_DBL\_RADIX\_LDBL\_RADIX**|指数表記の基数。|2 2 2|  
|**FLT\_ROUNDS\_DBL\_ROUNDS\_LDBL\_ROUNDS**|浮動小数点加算の丸めモード。|1 \(近く\) 1 \(近く\) 1 \(近く\)|  
  
 上記の表の情報は、将来の実装では変わる可能性があることに注意してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C 浮動小数点定数](../c-language/c-floating-point-constants.md)