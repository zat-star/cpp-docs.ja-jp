---
title: _get_tzname | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_tzname
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
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
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
ms.openlocfilehash: 7061018f217aec8a758b63697f3ef45dfbbdfa82
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="gettzname"></a>_get_tzname
タイム ゾーン名または夏時間ゾーン名 (DST) の文字列表現を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pReturnValue`  
 NULL 終端記号を含む `timeZoneName` の文字列の長さ。  
  
 [出力] `timeZoneName`  
 `index` に基づき、タイム ゾーン名または夏時間ゾーン名 (DST) の文字列のアドレス。  
  
 [入力] `sizeInBytes`  
 `timeZoneName` 文字列のサイズ (バイト単位)。  
  
 [入力] `index`  
 取得する 2 つのタイム ゾーン名のいずれかのインデックス。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は 0 を返し、それ以外の場合は `errno` タイプの値を返します。  
  
 `timeZoneName` が `NULL` である、または `sizeInBytes` が 0 か 0 未満のいずれかである場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|戻り値|`timeZoneName` の内容|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|TZ 名のサイズ|`NULL`|0|0 または 1|0|変更されない|  
|TZ 名のサイズ|任意|> 0|0 または 1|0|TZ 名|  
|変更されない|`NULL`|> 0|任意|`EINVAL`|変更されない|  
|変更されない|任意|ゼロ|任意|`EINVAL`|変更されない|  
|変更されない|任意|> 0|> 1|`EINVAL`|変更されない|  
  
## <a name="remarks"></a>コメント  
 `_get_tzname` 関数は、インデックス値に基づき、タイム ゾーン名または夏時間ゾーン名 (DST) の文字列表現を `pReturnValue` の文字列のサイズと共に取得して、`timeZoneName` のアドレスに入れます。 `timeZoneName` が `NULL` であり `sizeInBytes` がゼロの場合、どちらかのタイム ゾーンの文字列のサイズのみがバイト単位で `pReturnValue` に返されます。 インデックス値は、標準タイム ゾーンが 0、または夏時間ゾーンが 1 のいずれかでなければなりません。他のインデックス値では結果が未確定となります。  
  
### <a name="index-values"></a>インデックス値  
  
|`index`|`timeZoneName` の内容|`timeZoneName` の既定値|  
|-------------|--------------------------------|----------------------------------|  
|0|タイム ゾーン名|「PST」|  
|1|夏時間ゾーン名|「PDT」|  
|> 1 または < 0|`errno` を `EINVAL` に設定|変更されない|  
  
 実行時に値を明示的に変更しない限り、既定値はそれぞれ「PST」および「PDT」です。  これらの文字配列のサイズは `TZNAME_MAX` 値で管理されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [時間管理](../../c-runtime-library/time-management.md)   
 [errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)
