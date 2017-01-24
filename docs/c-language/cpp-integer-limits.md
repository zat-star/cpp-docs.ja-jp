---
title: "C++ 整数の制限 | Microsoft Docs"
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
  - "整数の制限"
  - "制限, 整数"
  - "制限, 整数定数"
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 整数の制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 次の表に、整数型の制限を示します。  これらの制限は、標準ヘッダー ファイル LIMITS.H で定義されます。  Microsoft C では、サイズ 8 ビット、16 ビット、または 32 ビットの整数型である、サイズ設定された整数変数も宣言できます。  サイズが設定された整数の詳細については、「[サイズ設定された整数型](../c-language/c-sized-integer-types.md)」を参照してください。  
  
### 整数定数の制限  
  
|**定数**|説明|値|  
|------------|--------|-------|  
|**CHAR\_BIT**|ビット フィールドではない最小変数のビット数。|8|  
|**SCHAR\_MIN**|**signed char** 型変数の最小値。|–128|  
|**SCHAR\_MAX**|**signed char** 型変数の最大値。|127|  
|**UCHAR\_MAX**|`unsigned char` 型変数の最大値。|255 \(0xff\)|  
|**CHAR\_MIN**|`char` 型変数の最小値。|\-128、\/J オプション使用時は 0|  
|**CHAR\_MAX**|`char` 型変数の最大値。|127、\/J オプション使用時は 255|  
|**MB\_LEN\_MAX**|多文字定数の最大バイト数。|5|  
|**SHRT\_MIN**|**short** 型変数の最小値。|–32768|  
|**SHRT\_MAX**|**short** 型変数の最大値。|32767|  
|**USHRT\_MAX**|**unsigned short** 型変数の最大値。|65535 \(0xffff\)|  
|**INT\_MIN**|`int` 型変数の最小値。|–2147483647 – 1|  
|**INT\_MAX**|`int` 型変数の最大値。|2147483647|  
|**UINT\_MAX**|`unsigned int` 型変数の最大値。|4294967295 \(0xffffffff\)|  
|**LONG\_MIN**|**long** 型変数の最小値。|–2147483647 – 1|  
|**LONG\_MAX**|**long** 型変数の最大値。|2147483647|  
|**ULONG\_MAX**|`unsigned long` 型変数の最大値。|4294967295 \(0xffffffff\)|  
  
 値が最大の整数表現を超えると、Microsoft コンパイラでエラーが生成されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C 整数定数](../Topic/C%20Integer%20Constants.md)