---
title: "例外 (C/C++) | Microsoft Docs"
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
  - "ERROR_MOD_NOT_FOUND"
  - "vcppException"
  - "ERROR_SEVERITY_ERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外処理, 遅延読み込み (DLL を)"
  - "遅延読み込み (DLL を), 例外"
  - "ERROR_MOD_NOT_FOUND 例外"
  - "ERROR_SEVERITY_ERROR 例外"
  - "vcppException"
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 例外 (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラーが見つかると、次の 2 つの例外コードが発生します。  
  
-   **LoadLibrary** エラーの例外コード  
  
-   **GetProcAddress** エラーの例外コード  
  
 例外情報は以下のとおりです。  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 スローされる例外コードは、標準の VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_MOD\_NOT\_FOUND\) 値と VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_PROC\_NOT\_FOUND\) 値です。  **DelayLoadInfo** 構造体へのポインターが LPDWORD 値で渡されます。**GetExceptionInformation** では、[EXCEPTION\_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) 構造体の ExceptionInformation\[0\] フィールドにこの値を取得します。  
  
 また、grAttrs フィールドで不正なビットが設定されている場合は、例外 ERROR\_INVALID\_PARAMETER がスローされます。  この例外は、どの点からみても致命的です。  
  
 詳細については、「[構造体と定数の定義](../../build/reference/structure-and-constant-definitions.md)」を参照してください。  
  
## 参照  
 [エラー処理と通知](../../build/reference/error-handling-and-notification.md)