---
title: _get_timezone | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_timezone
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
- _get_timezone
- get_timezone
dev_langs:
- C++
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 7ddada62e9bb209d8b5ffad6af3728edce36e443
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="gettimezone"></a>_get_timezone
協定世界時刻 (UTC) と現地時刻の秒単位の差を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `seconds`  
 UTC と現地時刻の秒単位の差。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0、エラーが発生した場合は `errno` 値。  
  
## <a name="remarks"></a>コメント  
 `_get_timezone` 関数は、UTC と現地時刻の秒単位の差を表す整数を取得します。 既定値は、太平洋標準時 (UTC から 8 時間遅れ) を表す 28,800 秒です。  
  
 `seconds` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_timezone`|\<time.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
