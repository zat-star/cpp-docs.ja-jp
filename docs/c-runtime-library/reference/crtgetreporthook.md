---
title: "_CrtGetReportHook | Microsoft Docs"
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
  - "_CrtGetReportHook"
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
  - "CrtGetReportHook"
  - "_CrtGetReportHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtGetReportHook 関数"
  - "_CrtGetReportHook 関数"
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtGetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デバッグ レポート プロセスのために C ランタイムにフックするクライアント定義レポート関数を取得します \(デバッグ バージョンのみ\)。  
  
## 構文  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## 戻り値  
 現在のクライアント定義レポート関数を返します。  
  
## 解説  
 `_CrtGetReportHook` は、C ランタイム デバッグ ライブラリのレポート プロセスのためにアプリケーションが現在のレポート関数を取得できるようにします。  
  
 フックをサポートするその他のランタイム関数の使い方の詳細と、独自のクライアント定義フック関数の記述方法については、「[デバッグ用フック関数の作成](../Topic/Debug%20Hook%20Function%20Writing.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtGetReportHook`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 使用例  
 `_CrtSetReportHook` の使用例については、「[report](http://msdn.microsoft.com/ja-jp/f6e08c30-6bd9-459a-830a-56deec0d2051)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)