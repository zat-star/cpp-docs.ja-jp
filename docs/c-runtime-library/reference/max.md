---
title: __max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __max
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
apitype: DLLExport
f1_keywords:
- max
- __max
dev_langs: C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 585d2a295bedb8b0ba49a893d5089bc682a1debd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="max"></a>__max
2 つの値のうち大きい方の値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 任意の数値のデータ型。  
  
 `a, b`  
 比較する数値型の値。  
  
## <a name="return-value"></a>戻り値  
 `__max` は、引数のうち大きい方の値を返します。  
  
## <a name="remarks"></a>コメント  
 `__max` マクロでは、2 つの値を比較して大きい方の値を返します。 引数には、符号付きまたは符号なしのすべての数値データ型を指定できます。 引数と戻り値はともに同じデータ型である必要があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>例  
 詳細については、「[__min](../../c-runtime-library/reference/min.md)」の例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)