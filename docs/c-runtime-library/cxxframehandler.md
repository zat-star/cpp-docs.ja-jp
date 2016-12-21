---
title: "__CxxFrameHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__CxxFrameHandler"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__CxxFrameHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__CxxFrameHandler"
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __CxxFrameHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

内部 CRT 関数。  構造化例外フレームを処理するために CRT によって使用されます。  
  
## 構文  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(       EHExceptionRecord  *pExcept,       EHRegistrationNode *pRN,       void               *pContext,        DispatcherContext  *pDC    )  
```  
  
#### パラメーター  
 `pExcept`  
 使用可能な `catch` ステートメントに渡される例外レコード。  
  
 `pRN`  
 例外を処理するために使用されるスタック フレームに関する動的な情報。  詳細については、「ehdata.h」を参照してください。  
  
 `pContext`  
 コンテキスト。  \(Intel プロセッサでは使用されません\)。  
  
 `pDC`  
 関数の開始とスタック フレームに関する追加情報。  
  
## 戻り値  
 [try\-except ステートメント](../cpp/try-except-statement.md) によって使用される*フィルター式*の値のいずれか。  
  
## 解説  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|\_\_CxxFrameHandler|excpt.h、ehdata.h|