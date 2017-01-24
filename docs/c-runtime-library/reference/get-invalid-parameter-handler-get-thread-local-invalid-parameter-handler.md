---
title: "_get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler | Microsoft Docs"
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
  - "_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_invalid_parameter_handler"
  - "stdlib/_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
  - "stdlib/_get_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "_get_thread_local_invalid_parameter_handler 関数"
  - "_get_invalid_parameter_handler 関数"
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT が無効な引数を検出したときに呼び出される関数を取得します。  
  
## 構文  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## 戻り値  
 現在設定されているポインター無効なパラメーター ハンドラー関数、または \[なし\] が設定されている場合は null ポインターです。  
  
## 解説  
 `_get_invalid_parameter_handler` 取得が現在設定されているグローバルの無効なパラメーター ハンドラー。 グローバルの無効なパラメーター ハンドラーが設定されていない場合は、null ポインターを返します。 同様に、 `_get_thread_local_invalid_parameter_handler` ハンドラーが設定されていない場合は、null ポインターで呼び出されるスレッドの現在のスレッド ローカルの無効なパラメーター ハンドラーを取得します。 グローバルとスレッド ローカルの無効なパラメーター ハンドラーを設定する方法については、次を参照してください。 [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)します。  
  
 返された無効なパラメーター ハンドラー関数ポインターには、次の種類があります。  
  
```c  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 無効なパラメーター ハンドラーの詳細については、「でプロトタイプ [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+ の場合: \< cstdlib \> または \< stdlib.h \>|  
  
 `_get_invalid_parameter_handler` と `_get_thread_local_invalid_parameter_handler` 関数は、Microsoft 固有の仕様です。 互換性の詳細を参照してください。 [互換性](../../c-runtime-library/compatibility.md)します。  
  
## 参照  
 [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [CRT 関数のセキュリティが強化されたバージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)