---
title: "_RTC_SetErrorFunc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_SetErrorFunc"
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
apitype: "DLLExport"
f1_keywords: 
  - "RTC_SetErrorFunc"
  - "_RTC_SetErrorFunc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RTC_SetErrorFunc 関数"
  - "_RTC_SetErrorFunc 関数"
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _RTC_SetErrorFunc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行時エラー チェック \(RTC\) を報告するためのハンドラーとして関数を指定します。 この関数は使用されなくなりました。代わりに `_RTC_SetErrorFuncW` をご使用ください。  
  
## 構文  
  
```  
  
_RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn  
 function   
);  
  
```  
  
#### パラメーター  
 *関数*  
 実行時エラー チェックを処理する関数のアドレス。  
  
## 戻り値  
 以前に定義されたエラーの関数。 以前に定義された関数がない場合は、NULL が返されます。  
  
## 解説  
 この関数は使用しないでください。代わりに `_RTC_SetErrorFuncW` をご使用ください。 これは下位互換性のためだけに残されています。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_CrtDbgReport、\_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [ランタイム エラー チェック](../Topic/Run-Time%20Error%20Checking.md)