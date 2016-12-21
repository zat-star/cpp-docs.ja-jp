---
title: "_RTC_NumErrors | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_NumErrors"
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
  - "_RTC_NumErrors"
  - "RTC_NumErrors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ランタイム エラー"
  - "_RTC_NumErrors 関数"
  - "RTC_NumErrors 関数"
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_NumErrors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行時エラー チェック \(RTC\) で検出できるエラーの合計数を返します。 この数値は **for** ループを制御するために使用し、ループ内では各値を [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md) に渡すことができます。  
  
## 構文  
  
```  
  
int _RTC_NumErrors( void );  
  
```  
  
## 戻り値  
 Visual C\+\+ の実行時エラー チェックで検出できるエラーの合計数を表す値を持つ整数。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_RTC_NumErrors`|\<rtcapi.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [ランタイム エラー チェック](../Topic/Run-Time%20Error%20Checking.md)