---
title: "_get_dstbias | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_dstbias"
  - "__dstbias"
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
  - "__dstbias"
  - "_get_dstbias"
  - "get_dstbias"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__dstbias"
  - "_get_dstbias 関数"
  - "夏時間のオフセット"
  - "get_dstbias 関数"
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_dstbias
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

夏時間のオフセット \(秒単位\) を取得します。  
  
## 構文  
  
```  
  
error_t _get_dstbias(      int* seconds );  
```  
  
#### パラメーター  
 `seconds`  
 夏時間のオフセット \(秒単位\)。  
  
## 戻り値  
 正常終了した場合は 0、エラーが発生した場合は `errno` 値。  
  
## 解説  
 `_get_dstbias` 関数は、夏時間の秒数を整数として取得します。  夏時間が適用されている場合、既定のオフセットは 3,600 秒であり、これは 1 時間の秒数です \(ただし、一部の地域は 2 時間のオフセットを実施しています\)。  
  
 `seconds` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 マクロ `_dstbias` または非推奨の関数 `__dstbias` の代わりに、この関数を使用することをお勧めします。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_dstbias`|\<time.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)