---
title: "時間管理 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- dates, run-time library members
- time, time management
- date functions
- time functions
ms.assetid: 93599220-c011-45d5-978f-12182abfdd2f
caps.latest.revision: 18
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 453cb5b598d2fca2e00cba9bb0a46cf0098eddec
ms.lasthandoff: 02/24/2017

---
# <a name="time-management"></a>時間管理
以下の関数を使用すると、現在の時刻を取得して、必要に応じて変換、調整、保存を行うことができます。 現在の時刻とはシステム時刻のことです。  
  
 `_ftime` および `localtime` ルーチンでは `TZ` 環境変数が使用されます。 `TZ` が設定されていない場合、ランタイム ライブラリはオペレーティング システムで指定されるタイム ゾーン情報を使用します。 この情報が使用できないとき、これらの関数では既定値 PST8PDT が使用されます。 `TZ` の詳細については、「[_tzset](../c-runtime-library/reference/tzset.md)」のほか、「[_daylight、timezone、および _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)」も参照してください。  
  
### <a name="time-routines"></a>時間のルーチン  
  
|関数|用途|同等の .NET Framework 関数|  
|--------------|---------|-------------------------------|  
|[asctime、_wasctime](../c-runtime-library/reference/asctime-wasctime.md)、[asctime_s、_wasctime_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|時刻を `struct tm` 型から文字列に変換します。 これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)、 [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)、 [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)、 [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)、 [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[clock](../c-runtime-library/reference/clock.md)|プロセスの実際の経過時間を返します。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)、[_ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|時刻を `time_t`型、 `__time32_t` 型、または `__time64_t` 型から文字列に変換します。 これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)、 [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)、 [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)、 [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)|  
|[difftime、_difftime32、_difftime64](../c-runtime-library/reference/difftime-difftime32-difftime64.md)|2 つの時刻の差を計算します。|[System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)|  
|[_ftime、_ftime32、_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)、[_ftime_s、_ftime32_s、_ftime64_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|`struct _timeb` 型または `struct``__timeb64` これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)|  
|[_futime、_futime32、_futime64](../c-runtime-library/reference/futime-futime32-futime64.md)|開いているファイルの変更時刻を設定します。|[System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)、 [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)、 [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)|  
|[gmtime、_gmtime32、_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)、[gmtime_s、_gmtime32_s、_gmtime64_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|時刻を `time_t` 型から `struct tm` に変換するか、`__time64_t` 型から `struct tm` に変換します。これらの関数のうち、`_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)、 [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[localtime、_localtime32、_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)、[localtime_s、_localtime32_s、_localtime64_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|時刻を `time_t` 型から `struct tm` に変換するか、 `__time64_t` 型から `struct tm`に変換します。 これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)|  
|[_mkgmtime、_mkgmtime32、_mkgmtime64](../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)|時刻をグリニッジ標準時のカレンダーの値に変換します。|[System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)|  
|[mktime、_mktime32、_mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md)|時刻をカレンダーの値に変換します。|[System::DateTime::DateTime](Overload:System.DateTime.)|  
|[_strdate、_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)、[_strdate_s、_wstrdate_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|現在のシステム日付を文字列として返します。 これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[strftime、wcsftime、_strftime_l、_wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|国際対応するように日付と時刻の文字列の書式を設定します。|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)、 [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)、 [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)、 [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)、 [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[_strtime、_wstrtime](../c-runtime-library/reference/strtime-wstrtime.md)、[_strtime_s、_wstrtime_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|現在のシステム時刻を文字列として返します。 これらの関数のうち、 `_s` サフィックスの付いているバージョンがより安全です。|[System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)、 [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)、 [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)、 [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)、 [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)|  
|[time、_time32、_time64](../c-runtime-library/reference/time-time32-time64.md)|`time_t`型、 `__time32_t` 型、または `__time64_t`型で、現在のシステム時刻を取得します。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_tzset](../c-runtime-library/reference/tzset.md)|時刻の環境変数 `TZ`で時刻の外部変数を設定します。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)|現在の時刻または構造体に格納された時刻の値を使用して、指定されたファイルの変更時刻を設定します。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
  
> [!NOTE]
>  Microsoft C/C++ バージョン 7.0 を除くすべてのバージョンの Microsoft C/C++ と、すべてのバージョンの Visual C++ で、時刻の関数は、現在の時刻を 1970 年 1 月 1 日の午前 0 時から経過した秒数として返します。 Microsoft C/C++ バージョン 7.0 では、 `time` は、現在の時刻を 1899 年 12 月 31 日の午前 0 時から経過した秒数として返していました。  
  
> [!NOTE]
>  Visual C++ 2005 より前のバージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] と Microsoft C/C++ では、 `time_t` は `long int` (32 ビット) であったため、2038 年 1 月 19 日 3 時 14 分 07 秒 (UTC) を超えた日付には使用できませんでした。 現在、既定で `time_t` は `__time64_t` と同じです。ただし、`_USE_32BIT_TIME_T` を定義すると、`time_t` は `__time32_t` に変更され、多くの時刻関数は強制的に 32 ビットの `time_t` を取得するバージョンを呼び出すことになります。 詳細については、「[基本データ型](../c-runtime-library/standard-types.md)」のほか、それぞれの時刻関数に関するドキュメントのコメントを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
