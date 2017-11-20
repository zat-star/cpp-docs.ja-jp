---
title: "_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_invalid_parameter_handler
- stdlib/_get_invalid_parameter_handler
- _get_thread_local_invalid_parameter_handler
- stdlib/_get_thread_local_invalid_parameter_handler
dev_langs: C++
helpviewer_keywords:
- _get_thread_local_invalid_parameter_handler function
- _get_invalid_parameter_handler function
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aef6cfa2c015abf64cdfd217e2128dd77bd925a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="getinvalidparameterhandler-getthreadlocalinvalidparameterhandler"></a>_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler
CRT が無効な引数を検出したときに呼び出される関数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## <a name="return-value"></a>戻り値  
 現在設定されている無効なパラメーター ハンドラー関数を指すポインター、または何も設定されていない場合は Null ポインターです。  
  
## <a name="remarks"></a>コメント  
 `_get_invalid_parameter_handler` 関数は、現在設定されている無効なグローバル パラメーター ハンドラーを取得します。 無効なグローバル パラメーター ハンドラーが設定されていない場合は、Null ポインターを返します。 同様に、`_get_thread_local_invalid_parameter_handler` は、自身が呼び出されるスレッドのスレッド ローカルの現在の無効なパラメーター ハンドラー、またはハンドラーが設定されていない場合は Null ポインターを取得します。 グローバルとスレッド ローカルの無効なパラメーター ハンドラーを設定する方法については、「[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)」を参照してください。  
  
 返される無効なパラメーター ハンドラー関数ポインターには、次の型があります。  
  
```C  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 無効なパラメーター ハンドラーの詳細については、「[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)」内のプロトタイプを参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \<stdlib.h><br /><br /> C++: \<cstdlib> または \<stdlib.h>|  
  
 `_get_invalid_parameter_handler` および `_get_thread_local_invalid_parameter_handler` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [CRT 関数のセキュリティが強化されたバージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)