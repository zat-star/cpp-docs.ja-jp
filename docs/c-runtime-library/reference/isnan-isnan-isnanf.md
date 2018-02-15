---
title: "isnan、_isnan、_isnanf | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isnan
- _isnanf
- isnan
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10d0997b1a6b304634c612f0f1615a059fd812b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="isnan-isnan-isnanf"></a>isnan、_isnan、_isnanf
浮動小数点値が非数 (NaN) かどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 テストする浮動小数点値。  
  
## <a name="return-value"></a>戻り値  
 C では、引数 `x` が NaN の場合、`isnan` マクロおよび `_isnan` と `_isnanf` の関数は 0 以外の値を返します。それ以外の場合は 0 を返します。  
  
 C++ では、引数 `x` が NaN の場合、`isnan` テンプレート関数は `true` を返します。それ以外の場合は `false` を返します。  
  
## <a name="remarks"></a>コメント  
 C の `isnan` マクロおよび `_isnan` と `_isnanf` の関数は、浮動小数点値 *x* をテストして、*x* が非数 (NaN) の値の場合は 0 以外の値を返します。 NaN は、浮動小数点演算の結果が IEEE-754 浮動小数点形式の指定した型で表現できない場合に生成されます。 出力で NaN が表現される方法の詳細については、「[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)」をご覧ください。  
  
 C++ としてコンパイルするとき、`isnan`マクロが定義されていないと、`isnan`テンプレート関数が代わりに定義されています。 型の値を返します`bool`整数ではなくです。  
  
 `_isnan` と `_isnanf` の関数は、Microsoft 固有の関数です。 `_isnanf` 関数は、x64 用にコンパイルするときにのみ使用できます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー (C)|必須ヘッダー (C++)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h>|\<math.h> または \<cmath>|  
|`_isnan`|\<float.h>|\<float.h> または \<cfloat>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_finite、_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass、_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)