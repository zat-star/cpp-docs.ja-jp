---
title: "_get_tzname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_tzname"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_tzname"
  - "get_tzname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_tzname 関数"
  - "get_tzname 関数"
  - "タイム ゾーン"
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_tzname
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タイム ゾーンの名前または daylight 標準時のタイム ゾーンの名前 \(DST\) の文字列表現を取得します。  
  
## 構文  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### パラメーター  
 \[出力\] `pReturnValue`  
 Null 終端文字など `timeZoneName` に文字列長を返します。  
  
 \[出力\] `timeZoneName`  
 `index`してタイム ゾーンの名前または daylight 標準時のタイム ゾーンの名前 \(DST\) 表現には文字列のアドレス。  
  
 \[入力\] `sizeInBytes`  
 バイトの `timeZoneName` の文字列のサイズ。  
  
 \[入力\] `index`  
 取得するする 2 種類のタイム ゾーンの名前の 1 種類のインデックス。  
  
## 戻り値  
 それ以外の場合は、`errno` 型の値が成功した場合はゼロ。  
  
 `timeZoneName` が `NULL`であるか、または `sizeInBytes` がゼロまたは未満ゼロ \(ただし、両方\) の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### エラー条件  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|戻り値|`timeZoneName` の内容|  
|--------------------|--------------------|-------------------|-------------|---------|------------------------|  
|TZ の名前のサイズ|`NULL`|0|0 または 1|0|変更されない|  
|TZ の名前のサイズ|任意|\> 0|0 または 1|0|TZ は名前を付けます。|  
|変更されない|`NULL`|\> 0|任意|`EINVAL`|変更されない|  
|変更されない|任意|0|任意|`EINVAL`|変更されない|  
|変更されない|任意|\> 0|\> 1|`EINVAL`|変更されない|  
  
## 解説  
 `_get_tzname` 関数は `pReturnValue`の文字列のサイズとともにインデックス値を使用して `timeZoneName` のアドレスにタイム ゾーンの名前または daylight 標準時のタイム ゾーンの名前 \(DST\) の文字列形式を、取得します。  `timeZoneName` が `NULL` であり、`sizeInBytes` がゼロの場合、バイトのタイム ゾーンの一連のサイズは、`pReturnValue`で返されます。  インデックス値は標準時タイム ゾーンの 0 または daylight 標準時のタイム ゾーンの必ず 1; インデックスのそのほかの値には不定の結果になります。  
  
### インデックス値  
  
|`index`|`timeZoneName` の内容|`timeZoneName` の 既定値|  
|-------------|------------------------|--------------------------|  
|0|タイム ゾーンの名前|「PST」|  
|1|Daylight 標準時のタイム ゾーンの名前|「PDT」|  
|\> 1 または \< 0|`errno` は `EINVAL`に設定します。|変更されない|  
  
 値が実行時中に明示的に変更するには、既定値「PST」、および「PDT」です。これらの文字配列のサイズは `TZNAME_MAX` 値によって決まります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_tzname`|\<time.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME\_MAX](../Topic/TZNAME_MAX.md)