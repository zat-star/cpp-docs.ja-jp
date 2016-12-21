---
title: "_set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler | Microsoft Docs"
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
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
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
  - "set_invalid_parameter_handler"
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "無効なパラメーター ハンドラー"
  - "set_invalid_parameter_handler 関数"
  - "_set_invalid_parameter_handler 関数"
  - "_set_thread_local_invalid_parameter_handler 関数"
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CRT が無効な引数を検出したときに呼び出される関数を設定します。  
  
## 構文  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### パラメーター  
 \[入力\] `pNew`  
 新しいの無効なパラメーター ハンドラーを関数ポインター。  
  
## 戻り値  
 呼び出しの前に無効なパラメーター ハンドラーへのポインター。  
  
## 解説  
 多くの C ランタイム関数は、渡された引数の有効性を確認します。 無効な引数が渡される場合、関数を設定できます、 `errno` エラー番号または戻り値はエラー コード。 このような場合は、無効なパラメーター ハンドラーが呼び出されます。 C ランタイムでは、プログラムを終了して、ランタイム エラー メッセージが表示される既定のグローバルの無効なパラメーター ハンドラーを提供します。 使用することができます、 `_set_invalid_parameter_handler` グローバルの無効なパラメーター ハンドラーとして独自の関数を設定します。 C ランタイムには、スレッド ローカルの無効なパラメーター ハンドラーもサポートしています。 使用して、スレッドでスレッド ローカル パラメーター ハンドラーを設定かどうか `_set_thread_local_invalid_parameter_handler`, 、スレッドから呼び出された C ランタイム関数がグローバル ハンドラーではなくそのハンドラーを使用します。 1 つの機能は、無効な引数がグローバル ハンドラーとして一度に指定できます。 1 つの機能は、1 つのスレッド、スレッド ローカルの無効な引数ハンドラーとして指定できますが、別のスレッドが別のスレッド ローカル ハンドラーを持つことができます。 これにより、他のスレッドの動作に影響を与えずに、コードの 1 つの部分で使用するハンドラーを変更できます。  
  
 ランタイムが無効なパラメーターの関数を呼び出すとは、通常回復不可能なエラーが発生したことを意味します。 指定した無効なパラメーター ハンドラー関数を中止し、データ保存してください。 エラーが回復可能であることを確認して main 関数に制御を返すことはできません。  
  
 無効なパラメーター ハンドラー関数には、次のプロトタイプが必要です。  
  
```c  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 `expression` 引数が、エラーが発生し、引数式のワイド文字列表現。`function` 引数は無効な引数を受け取った CRT 関数の名前。`file` 引数は、関数を含む CRT ソース ファイルの名前。`line` 引数は、そのファイル内の行番号。 最後の引数が予約されています。 すべてのパラメーター値を持つ `NULL` CRT ライブラリのデバッグ バージョンを使用しない場合。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+ の場合: \< cstdlib \> または \< stdlib.h \>|  
  
 `_set_invalid_parameter_handler` と `_set_thread_local_invalid_parameter_handler` 関数は、Microsoft 固有の仕様です。 互換性の詳細を参照してください。 [互換性](../../c-runtime-library/compatibility.md)します。  
  
## 使用例  
 次の例では、無効なパラメーター エラー ハンドラーが CRT ソースの無効なパラメーターおよびファイルと行を受け取った関数を印刷するために使用します。 したら CRT デバッグ ライブラリを使用すると、無効なパラメーター エラーも発生する、アサーションは、使用して、この例では無効 [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)します。  
  
```c  
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
無効なパラメーターが関数 common_vfprintf で検出されました。 ファイル: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp 行: 32 式: 形式! nullptr を =  
```  
  
## 参照  
 [\_get\_invalid\_parameter\_handler \_get\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [CRT 関数のセキュリティが強化されたバージョン](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)