---
title: feraiseexcept | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- feraiseexcept
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
- feraiseexcept
- fenv/feraiseexcept
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaa1848af2c8a7831017f6332afa988c305fe05
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="feraiseexcept"></a>feraiseexcept
指定した浮動小数点例外を発生させます。  
  
## <a name="syntax"></a>構文  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `excepts`  
 発生させる浮動小数点例外。  
  
## <a name="return-value"></a>戻り値  
 指定したすべての例外が正常に発生した場合は、0 を返します。  
  
## <a name="remarks"></a>コメント  
 `feraiseexcept` 関数は、`excepts` で指定された浮動小数点例外を発生させようとします。   `feraiseexcept` 関数は、\<fenv.h> に定義されている次の例外処理マクロをサポートしています。  
  
|例外処理マクロ|説明|  
|---------------------|-----------------|  
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|  
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|  
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|  
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|  
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|  
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|  
  
 `excepts` 引数は、0、例外処理マクロ値のいずれか、または複数のサポートされる例外処理マクロのビット演算 OR の場合があります。 指定した例外処理マクロのいずれかが FE_OVERFLOW または FE_UNDERFLOW の場合、副作用として FE_INEXACT 例外が発生する可能性があります。  
  
 この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
 **Microsoft 固有:** `excepts` に指定した例外は、FE_INVALID、FE_DIVBYZERO、FE_OVERFLOW、FE_UNDERFLOW、FE_INEXACT の順に発生します。 ただし、`excepts` に指定されていない場合でも、FE_OVERFLOW または FE_UNDERFLOW が発生したときに FE_INEXACT を発生させることができます。 **END Microsoft 固有の仕様**  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`feraiseexcept`|\<fenv.h>|\<cfenv>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)