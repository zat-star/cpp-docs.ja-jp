---
title: "fpclassify | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fpclassify
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81a2c9c5237d455908e1d0e4f58bff87418a7f8b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="fpclassify"></a>fpclassify
引数の浮動小数点の分類を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `x`  
 テストする浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 `fpclassify` 関数は、引数 `x` の浮動小数点の分類を示す整数値を返します。 次の表に、`fpclassify` が返す可能性がある、\<math.h> に定義された値を示します。  
  
|[値]|説明|  
|-----------|-----------------|  
|`FP_NAN`|クワイエット型、シグナル型、または不確定の NaN|  
|`FP_INFINITE`|正または負の無限大|  
|`FP_NORMAL`|正規化された正または負の 0 以外の値|  
|`FP_SUBNORMAL`|正規化されない正または負の値|  
|`FP_ZERO`|正または負の 0 値|  
  
## <a name="remarks"></a>コメント  
 C では、`fpclassify` はマクロです。C++ では、`fpclassify` は、`float`、`double`、または `long double` の引数の型を使用してオーバーロードされた関数です。 どちらの場合も、返される値は、中間表記ではなく、引数式の有効な型に依存します。 たとえば、`double` または `long double` の正規化値は、`float` に変換すると、無限大値、非正規化値、またはゼロ値になります。  
  
## <a name="requirements"></a>必要条件  
  
|関数/マクロ|必須ヘッダー (C)|必須ヘッダー (C++)|  
|---------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<math.h>|\<math.h> または \<cmath>|  
  
 `fpclassify` マクロと `fpclassify` 関数は、C99 および C++ 11 仕様に準拠しています。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)