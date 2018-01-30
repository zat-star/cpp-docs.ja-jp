---
title: "整数の制限値 |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5fc79f225d340777751ca513c0fb47dd33e17ad
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2018
---
# <a name="integer-limits"></a>整数の制限

**Microsoft 固有の仕様**

次の表に、整数型の制限を示します。 これらの制限は、標準ヘッダー ファイルの < limits.h > でも定義されます。

## <a name="limits-on-integer-constants"></a>整数定数の制限

|定数|説明|[値]|
|--------------|-------------|-----------|
|**CHAR_BIT**|ビット フィールドではない最小変数のビット数。|9|
|**SCHAR_MIN**|**signed char** 型変数の最小値。|-128|
|**SCHAR_MAX**|**signed char** 型変数の最大値。|127|
|**UCHAR_MAX**|型の変数の最大値**unsigned char**です。|255 (0xff)|
|**CHAR_MIN**|型の変数の最小値**char**です。|-128 (/J オプションが使用される場合は 0)|
|**CHAR_MAX**|型の変数の最大値**char**です。|-127 (/J オプションが使用される場合は 255)|
|**MB_LEN_MAX**|多文字定数の最大バイト数。|5|
|**SHRT_MIN**|**short** 型変数の最小値。|-32768|
|**SHRT_MAX**|**short** 型変数の最大値。|32767|
|**USHRT_MAX**|**unsigned short** 型変数の最大値。|65535 (0xffff)|
|**INT_MIN**|型の変数の最小値**int**です。|-2147483648|
|**INT_MAX**|型の変数の最大値**int**です。|2147483647|
|**UINT_MAX**|型の変数の最大値**符号なし int**です。|4294967295 (0xffffffff)|
|**LONG_MIN**|**long** 型変数の最小値。|-2147483648|
|**LONG_MAX**|**long** 型変数の最大値。|2147483647|
|**ULONG_MAX**|型の変数の最大値**unsigned long**です。|4294967295 (0xffffffff)|
|**LLONG_MIN**|型の変数の最小値**long**|-9223372036854775808|
|**LLONG_MAX**|型の変数の最大値**long**|9223372036854775807|
|**ULLONG_MAX**|型の変数の最大値**unsigned long long 型**|18446744073709551615 (0xffffffffffffffff)|

値が最大の整数表現を超えると、Microsoft コンパイラでエラーが生成されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[浮動小数点の制限](../cpp/floating-limits.md)  
