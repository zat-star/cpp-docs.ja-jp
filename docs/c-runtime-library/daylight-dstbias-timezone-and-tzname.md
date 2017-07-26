---
title: "_daylight、_dstbias、_timezone、_tzname | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
dev_langs:
- C++
helpviewer_keywords:
- time zones
- time adjustments
- timezone variables
- _tzname function
- _daylight function
- _timezone function
- daylight function
- local time adjustments
- timezone function
- tzname function
- time-zone variables
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 0b2b40db8d478eeb1570022bd1c901c2c28a883b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="daylight-dstbias-timezone-and-tzname"></a>_daylight、_dstbias、_timezone、および _tzname
`_daylight`、`_dstbias`、`_timezone`、`_tzname` は、日付と時刻に関する一部のルーチンでローカル時刻の調整に使われます。 これらのグローバル変数は使われなくなりました。セキュリティを強化したバージョンを代わりに使う必要があります。  
  
|グローバル変数|機能的に同等なバージョン|  
|---------------------|---------------------------|  
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 これらは、Time.h で次のように宣言されています。  
  
## <a name="syntax"></a>構文  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## <a name="remarks"></a>コメント  
 `_ftime`、`localtime`、`_tzset` の呼び出しで、`_daylight`、`_dstbias`、`_timezone`、`_tzname` の値は、`TZ` 環境変数の値によって決まります。 `TZ` の値を明示的に設定していない場合、`_tzname[0]` と `_tzname[1]` にはそれぞれ既定値である "PST" と "PDT" が設定されます。  時間操作関数 ([_tzset](../c-runtime-library/reference/tzset.md)、[_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md)、[localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) は、`_daylight`、`_dstbias`、`_timezone` の値を、オペレーティング システムで各変数の既定値をクエリすることによって設定します。 タイムゾーン グローバル変数の値を次の表に示します。  
  
|変数|値|  
|--------------|-----------|  
|`_daylight`|夏時間 (DST) ゾーンであることが `TZ` で指定されている場合、またはオペレーティング システムから特定される場合は 0 以外の値。それ以外の場合は 0。 既定値は 1 です。|  
|`_dstbias`|夏時間のオフセット。|  
|`_timezone`|協定世界時刻と現地時刻の差 (秒単位)。 既定値は 28,800 です。|  
|`_tzname[0]`|`TZ` 環境変数から得られるタイムゾーン名。 既定値は "PST" です。|  
|`_tzname[1]`|`TZ` 環境変数から得られる DST ゾーン名。 既定値は "PDT" (太平洋夏時間) です。|  
  
## <a name="see-also"></a>関連項目  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)
