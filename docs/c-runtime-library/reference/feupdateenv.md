---
title: feupdateenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feupdateenv
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
- feupdateenv
- fenv/feupdateenv
dev_langs: C++
helpviewer_keywords: feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c84e829876282a43fb9a8a17713a612e387f5216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="feupdateenv"></a>feupdateenv
現在発生している浮動小数点例外を保存し、指定した浮動小数点環境状態を復元し、保存されている浮動小数点例外を発生させます。  
  
## <a name="syntax"></a>構文  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `penv`  
 [fegetenv](fegetenv1.md) または [feholdexcept](feholdexcept2.md) を呼び出して設定される浮動小数点環境を含む `fenv_t` オブジェクトへのポインター。 また、FE_DFL_ENV マクロを使用して、既定のスタートアップ浮動小数点環境を指定することもできます。  
  
## <a name="return-value"></a>戻り値  
 すべてのアクションが正常に完了した場合は、0 を返します。 それ以外の場合は、0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 `feupdateenv` 関数は複数のアクションを実行します。 まず、現在発生している浮動小数点例外状態フラグを自動ストレージに格納します。 次に、`penv` が示す `fenv_t` オブジェクトに格納されている値から現在の浮動小数点環境を設定します。 `penv` が FE_DFL_ENV ではない場合、または有効な `fenv_t` オブジェクトを示していない場合、その後の動作は未定義になります。 最後に、`feupdateenv` は、ローカルに格納されている浮動小数点例外を発生させます。  
  
 この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|関数|C ヘッダー|C++ ヘッダー|  
|--------------|--------------|------------------|  
|`feupdateenv`|\<fenv.h>|\<cfenv>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)