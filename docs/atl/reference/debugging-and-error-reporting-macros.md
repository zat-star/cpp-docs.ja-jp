---
title: "デバッグとエラー レポートに関するマクロ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マクロ, エラーの報告"
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# デバッグとエラー レポートに関するマクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのマクロは、有効なデバッグ提供し、機能をたどります。  
  
|||  
|-|-|  
|[\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md)|には、\[出力\]ウィンドウに、`_Module.Term` が呼び出されたときに検出されたインターフェイスのリークを書き込みます。|  
|[\_ATL\_DEBUG\_QI](../Topic/_ATL_DEBUG_QI.md)|`QueryInterface` への呼び出しをすべて出力ウィンドウに書き込みます。|  
|[ATLASSERT](../Topic/ATLASSERT.md)|C ランタイム ライブラリにある [\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) のマクロと同じ機能を実行します。|  
|[ATLENSURE](../Topic/ATLENSURE.md)|パラメーターの検証を実行します。  呼び出し `AtlThrow` 必要に応じて|  
|[ATLTRACENOTIMPL](../Topic/ATLTRACENOTIMPL.md)|指定した関数が実行されないことダンプ デバイスにメッセージを送信します。|  
|[ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を送ります。  下位互換性のためにインクルードされます。|  
|[ATLTRACE2](../Topic/ATLTRACE2.md)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなどの出力デバイスに警告を送ります。|  
  
## 参照  
 [マクロ](../../atl/reference/atl-macros.md)   
 [デバッグとエラー報告に関するグローバル関数](../../atl/reference/debugging-and-error-reporting-global-functions.md)