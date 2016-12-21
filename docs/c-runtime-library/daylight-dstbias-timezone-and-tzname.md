---
title: "_daylight、_dstbias、_timezone、および _tzname | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "タイム ゾーン"
  - "時間調整"
  - "タイムゾーン変数"
  - "_tzname 関数"
  - "_daylight 関数"
  - "_timezone 関数"
  - "daylight 関数"
  - "現地時刻の調整"
  - "timezone 関数"
  - "tzname 関数"
  - "タイム ゾーン変数"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _daylight、_dstbias、_timezone、および _tzname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_daylight`、`_dstbias`、`_timezone`と `_tzname` は、時間と日付のルーチンで現地時間の調整に使用されます。  これらのグローバル変数はグローバル変数の代わりに使用する必要のある機能のセキュリティを強化したバージョンについては推奨されていません。  
  
|グローバル変数|等価機能|  
|-------------|----------|  
|`_daylight`|[\_get\_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[\_get\_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[\_get\_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 これらは Time.h に次のように宣言されます。  
  
## 構文  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## 解説  
 `_ftime`への呼び出しで、`localtime`、または `_tzset`の `_daylight`、`_dstbias`、`_timezone`と `_tzname` の値は `TZ` の環境変数の値によって決定されます。  明示的に `TZ`の値を設定すると、`_tzname[0]``_tzname[1]` は「PST」および「PDT」の既定の設定を個別に含まれています。時刻操作関数 \([\_tzset](../Topic/_tzset.md)、[\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md)と [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)\) は変数の既定値のオペレーティング システムを照会することによって、`_daylight``_dstbias` と `_timezone` の値を設定しようとします。  タイム ゾーンのグローバル変数の値を次の表に示します。  
  
|変数|値|  
|--------|-------|  
|`_daylight`|夏時間 \(DST\) のゾーンが `TZ` で指定されたディレクトリまたはオペレーティング システムで設定されている場合 0 以外の; それ以外の場合は 0。  既定値は 1 です。|  
|`_dstbias`|夏時間のオフセット。|  
|`_timezone`|世界協定時刻と現地時間間隔の秒の差を計算します。  既定値は 28,800 です。|  
|`_tzname[0]`|タイム ゾーンの名前は `TZ` 環境変数から派生しました。  既定値は "PST" です。|  
|`_tzname[1]`|DST ゾーンの名前は `TZ` 環境変数から派生しました。  既定値は「PDT」 \(太平洋夏時間\)。|  
  
## 参照  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)