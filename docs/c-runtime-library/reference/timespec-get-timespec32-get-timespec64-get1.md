---
title: "timespec_get、_timespec32_get、_timespec64_get1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
dev_langs: C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 681f9d125a7f45dae2a8e604df655facdd246067
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get、_timespec32_get、_timespec64_get
指定された時間の基準に基づいて、最初の引数が指す間隔を現在のカレンダーの時間に設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `time_spec`  
 エポックの開始以降の時間 (秒およびナノ秒単位) に設定される構造体へのポインター。  
  
 `base`  
 時間の基準を指定する実装固有の値 (0 以外)。  
  
## <a name="return-value"></a>戻り値  
 成功すると値は `base` になり、失敗すると 0 を返します。  
  
## <a name="remarks"></a>コメント  
 `timespec_get` 関数は、 `time_spec` 引数が指す構造体で現在の値を設定します。 構造体のすべてのバージョンには、 `tv_sec` 、 `tv_nsec`というメンバーが存在します。 `tv_sec` 値は整数の秒に設定され、 `tv_nsec` はナノ秒の整数に設定されます ( `base`によって指定されるエポックの開始以降の、システム クロックの解像度に丸められます)。  
  
 **Microsoft 固有の仕様**  
  
 これらの関数は、 `TIME_UTC` 値として `base` のみをサポートしています。 これは、 `time_spec` 値をエポック開始 (1970 年 1 月 1 日午前0 時の世界協定時刻 (UTC)) 以降の秒数およびナノ秒数に設定します。 `struct _timespec32`では、 `tv_sec` は `__time32_t` 値です。 `struct _timespec64`では、 `tv_sec` は `__time64_t` 値です。 `struct timespec`では、 `tv_sec` は `time_t` 型です。この長さは、プロセッサ マクロ _USE_32BIT_TIME_T が定義されているかどうかに応じて 32 ビットまたは 64 ビットになります。 `timespec_get` 関数は、_USE_32BIT_TIME_T が定義されている場合には `_timespec32_get` を呼び出し、定義されていない場合には `_timespec64_get`を呼び出すインライン関数です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`timespec_get`では、 `_timespec32_get`では、 `_timespec64_get`|C: \<time.h>、C++: \<ctime> または \<time.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)