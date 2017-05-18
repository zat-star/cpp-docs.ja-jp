---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
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
ms.openlocfilehash: e86ea8aa561af584a6825d4225820aca7baeced2
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="srand"></a>srand
擬似乱数ジェネレーターのシード開始値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `seed`  
 擬似乱数ジェネレーターのシード  
  
## <a name="remarks"></a>コメント  
 `srand` 関数は、現在のスレッドに一連の整数の擬似乱数を生成するための開始点を設定します。 ジェネレーターを最初期化して、結果の同じシーケンスを作成するには、`srand` 関数を呼び出し、同じ `seed` 引数を再度使用します。 `seed` のその他の値は、擬似乱数シーケンスのさまざまな開始位置にジェネレーターを設定します。 `rand` は、生成される擬似乱数を取得します。 `rand` に対する呼び出しの前に `srand` を呼び出すと、1 として渡された `srand` を使用して `seed` を呼び出すのと同じシーケンスが生成されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`srand`|\<stdlib.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 「[rand](../../c-runtime-library/reference/rand.md)」の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
