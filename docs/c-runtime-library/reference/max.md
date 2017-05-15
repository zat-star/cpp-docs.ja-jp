---
title: __max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __max
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
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a73c66cc0d1e49c514f8f451aa01a0c8ca7a9277
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

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
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>例  
 詳細については、「[__min](../../c-runtime-library/reference/min.md)」の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)
