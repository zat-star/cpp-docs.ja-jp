---
title: _get_daylight | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __daylight
- _get_daylight
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_daylight
- _get_daylight
dev_langs:
- C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
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
ms.openlocfilehash: 298f293e5ea0533fb27ae8c259900bc4f1cd0d2a
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="getdaylight"></a>_get_daylight
夏時間のオフセット (時間単位) を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      error_t _get_daylight(   
    int* hours  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hours`  
 夏時間のオフセット (時間単位)。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0、エラーが発生した場合は `errno` 値。  
  
## <a name="remarks"></a>コメント  
 `_get_daylight` 関数は、夏時間の時間数を整数として取得します。 夏時間が有効な場合、既定のオフセットは 1 時間です (ただし、一部の地域は 2 時間のオフセットを実施しています)。  
  
 `hours` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 マクロ `_daylight` または非推奨の関数 `__daylight` の代わりに、この関数を使用することをお勧めします。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_daylight`|\<time.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
