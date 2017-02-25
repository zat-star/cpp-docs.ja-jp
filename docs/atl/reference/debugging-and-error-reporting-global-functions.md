---
title: "デバッグとエラー報告に関するグローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数 [ATL], エラーの報告"
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# デバッグとエラー報告に関するグローバル関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらの関数は、有効なデバッグ提供し、機能をたどります。  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|HRESULT の形式で `GetLastError` のエラー コードを返します。|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Win32 エラー コードを HRESULT に変換します。|  
|[AtlReportError](../Topic/AtlReportError.md)|**IErrorInfo** をクライアントにエラーの詳細を表示するように設定します。|  
|[AtlThrow](../Topic/AtlThrow.md)|`CAtlException` をスローします。|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Windows の `GetLastError` 関数の結果に基づいてエラーを通知します。|  
|[AtlTraceLoadSettings](../../misc/atltraceloadsettings.md)|ファイルからトレース設定を読み込みます。|  
|[AtlTraceSaveSettings](../../misc/atltracesavesettings.md)|現在のトレース設定をファイルに保存します。|  
  
## 参照  
 [関数](../../atl/reference/atl-functions.md)   
 [デバッグとエラー レポートに関するマクロ](../../atl/reference/debugging-and-error-reporting-macros.md)