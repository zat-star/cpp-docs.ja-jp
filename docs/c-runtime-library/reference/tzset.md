---
title: _tzset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _tzset
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
f1_keywords: _tzset
dev_langs: C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f103da7ca67721f6c654c593746b9427954c6930
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tzset"></a>_tzset
時間環境変数を設定します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「                  [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>コメント  
 `_tzset` 関数は環境変数 `TZ` の現在の設定を使用して、 `_daylight`、 `_timezone`、および `_tzname`の 3 つのグローバル変数に値を代入します。 これらの変数は、 [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 関数と [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 関数によって世界協定時刻 (UTC: Coordinated Universal Time) から現地時刻へ修正するために使用されます。また `time` 関数によってシステム時刻から UTC を計算するのに使用されます。 `TZ` 環境変数を設定するには、次の構文を使用します。  
  
 `set` `TZ`=`tzn`[+ &#124; -]`hh`[`:mm`[`:ss`] ][`dzn`]  
  
 `tzn`  
 PST など、3 文字のタイム ゾーンの名前。 現地時刻から UTC への適切なオフセットを指定する必要があります。  
  
 `hh`  
 UTC と現地時刻の時差。 正の値のための符号 (+) オプション。  
  
 `mm`  
 分。 コロン ( `hh` ) で`:`との間を区切ります。  
  
 `ss`  
 秒。 コロン ( `mm` ) で`:`との間を区切ります。  
  
 `dzn`  
 PDT など、3 文字の夏時間のタイム ゾーン。 その地域で夏時間が実施されていない場合は、 `TZ` の値を指定しないで `dzn`を設定します。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。  
  
> [!NOTE]
>  計算時には時差の符号に注意してください。 時差は現地時刻から UTC に変換する場合のオフセットである (逆ではない) であるため、符号は直感的に考えるものとは逆である場合があります。 UTC より早いタイム ゾーンの場合、時差は負になります。UTC より遅い場合、時差は正になります。  
  
 たとえば、 `TZ` 環境変数を現在のドイツのタイム ゾーンに対応するように設定する場合は、コマンド ラインに次のように入力します。  
  
```  
set TZ=GST-1GDT  
```  
  
 このコマンドは、GST によってドイツの標準時刻であることを示し、UTC がドイツの時刻よりも 1 時間遅い (またはドイツは UTC より 1 時間早い) と想定し、さらにドイツでは夏時間が採用されていると想定しています。  
  
 場合、`TZ`値が設定されていない`_tzset`オペレーティング システムで指定されたタイム ゾーン情報を使用しようとしています。 Windows オペレーティング システムの場合、この情報は [コントロール パネル] の [日付/時刻] で指定します。 `_tzset` でこの情報を取得できない場合、既定では太平洋標準時タイム ゾーンを表す PST8PDT が使用されます。  
  
 `TZ` が呼び出されると、 `_daylight`の環境変数の値に基づいて、次の値がグローバル変数 `_timezone`、 `_tzname` 、および `_tzset` に代入されます。  
  
|グローバル変数|説明|既定値|  
|---------------------|-----------------|-------------------|  
|`_daylight`|夏時間のタイム ゾーンが `TZ` の設定で指定されている場合は 0 以外の値、指定されていない場合は 0。|1|  
|`_timezone`|現地時刻と UTC の秒単位での時差。|28800 (28800 秒は 8 時間に相当)|  
|`_tzname`[0]|`TZ` の環境変数のタイム ゾーンの名前の文字列値。 `TZ` が設定されていない場合は空。|PST|  
|`_tzname`[1]|夏時間のタイム ゾーンの文字列値。`TZ` の環境変数の値に夏時間のタイム ゾーンが含まれていない場合は空。|PDT|  
  
 上の表に示されている `_daylight` に対する既定値と `_tzname` の配列は "PST8PDT" に対応します。 DST のゾーンが `TZ` の環境変数に含まれていない場合は、 `_daylight` の値は 0 で、 `_ftime`、 `gmtime`、および `localtime` の各関数はそれぞれの DST フラグに対して 0 を返します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_tzset`|\<time.h>|  
  
 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_tzset.cpp  
// This program uses _tzset to set the global variables  
// named _daylight, _timezone, and _tzname. Since TZ is  
// not being explicitly set, it uses the system time.  
  
#include <time.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    _tzset();  
    int daylight;  
    _get_daylight( &daylight );  
    printf( "_daylight = %d\n", daylight );  
    long timezone;  
    _get_timezone( &timezone );  
    printf( "_timezone = %ld\n", timezone );  
    size_t s;  
    char tzname[100];  
    _get_tzname( &s, tzname, sizeof(tzname), 0 );  
    printf( "_tzname[0] = %s\n", tzname );  
    exit( 0 );  
}  
```  
  
```Output  
_daylight = 1  
_timezone = 28800  
_tzname[0] = Pacific Standard Time  
```  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)