---
title: "_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
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
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7827b8c538a90c39c0dc32320aaab01ada7e2318
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setinvalidparameterhandler-setthreadlocalinvalidparameterhandler"></a>_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler
CRT が無効な引数を検出したときに呼び出される関数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `pNew`  
 新しい無効なパラメーター ハンドラーへの関数ポインターです。  
  
## <a name="return-value"></a>戻り値  
 呼び出し前の無効なパラメーター ハンドラーへのポインターです。  
  
## <a name="remarks"></a>コメント  
 多くの C ランタイム関数では、渡された引数の有効性を確認しています。 無効な引数を渡された場合、関数では `errno` エラー番号を設定するか、エラー コードを返すことができます。 このような場合、無効なパラメーター ハンドラーも呼び出されます。 C ランタイムでは、プログラムを終了してランタイム エラー メッセージを表示する、既定のグローバルの無効なパラメーター ハンドラーを提供しています。 `_set_invalid_parameter_handler` を使用すると、独自の関数をグローバルの無効なパラメーター ハンドラーとして設定できます。 C ランタイムでは、スレッド ローカルの無効なパラメーター ハンドラーもサポートしています。 `_set_thread_local_invalid_parameter_handler` を使用してスレッド ローカル パラメーター ハンドラーをスレッド内で設定した場合、そのスレッドから呼び出された C ランタイム関数ではグローバル ハンドラーではなくそのハンドラーを使用します。 グローバルの無効な引数ハンドラーとしては、同時に 1 つの関数しか指定できません。 1 つのスレッド内では 1 つの関数しかスレッド ローカルの無効な引数ハンドラーとして指定できませんが、別のスレッドでは別のスレッド ローカルなハンドラーを持つことができます。 これにより、コードの一部で使用するハンドラーを、他のスレッドの動作に影響を与えずに変更できます。  
  
 通常、ランタイムが無効なパラメーター関数を呼び出したということは、回復不可能なエラーが発生したことを意味します。 提供する無効なパラメーター ハンドラー関数は、保存できるデータを保存してから中止処理をしなければなりません。 エラーが回復可能であるという確信を持てない限り、main 関数に制御を返すべきではありません。  
  
 無効なパラメーター ハンドラー関数には以下のプロトタイプが必要です。  
  
```  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 `expression` 引数は、エラーを発生させた引数式のワイド文字列表記です。 `function` 引数は、無効な引数を受け取った CRT 関数の名前です。 `file` 引数は、関数を含む CRT ソース ファイルの名前です。 `line` 引数は、そのファイル内での行番号です。 最後の引数は予約済みです。 CRT ライブラリのデバッグ バージョンが使用されている場合を除き、パラメーターはすべて `NULL` 値を持ちます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \<stdlib.h><br /><br /> C++: \<cstdlib> または \<stdlib.h>|  
  
 `_set_invalid_parameter_handler` および `_set_thread_local_invalid_parameter_handler` の各関数は、Microsoft 固有の関数です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、無効なパラメーターを受け取った関数および CRT ソースのファイル名と行番号を出力するために、無効なパラメーター エラー ハンドラーが使用されています。 デバッグ CRT ライブラリを使用した場合、無効なパラメーター エラーによってアサーションも発生しますが、この例では [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) を使用してアサーションが無効化されています。  
  
```C  
// crt_set_invalid_parameter_handler.c  
// compile with: /Zi /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
  
void myInvalidParameterHandler(const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter detected in function %s."  
            L" File: %s Line: %d\n", function, file, line);  
   wprintf(L"Expression: %s\n", expression);  
   abort();  
}  
  
int main( )  
{  
   char* formatString;  
  
   _invalid_parameter_handler oldHandler, newHandler;  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   // Call printf_s with invalid parameters.  
  
   formatString = NULL;  
   printf(formatString);  
}  
```  
  
```Output  
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32  
Expression: format != nullptr  
```  
  
## <a name="see-also"></a>参照  
 [_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [CRT 関数のセキュリティが強化されたバージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)