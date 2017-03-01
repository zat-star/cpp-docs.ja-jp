---
title: "_invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 49ae87567cd311e271a0ab50d7112a4a8f0c1b4a
ms.lasthandoff: 02/24/2017

---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson
これらの関数は、CRT ライブラリ関数に渡された有効でないパラメーターを処理するために C ランタイム ライブラリによって使用されます。 有効でないパラメーターの既定の処理またはカスタマイズ可能な処理をサポートするために、自分のコードでこれらの関数を使用することもできます。

## <a name="syntax"></a>構文
```
extern "C" void __cdecl 
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);  

extern "C" void __cdecl 
_invalid_parameter_noinfo(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invalid_parameter_noinfo_noreturn(void);  

extern "C" __declspec(noreturn) void __cdecl 
_invoke_watson(  
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="return-value"></a>戻り値
これらの関数は値を返しません。 `_invalid_parameter_noinfo_noreturn` および `_invoke_watson` 関数は呼び出し元に戻りません。`_invalid_parameter` および `_invalid_parameter_noinfo` は呼び出し元に戻らない可能性があります。

## <a name="parameters"></a>パラメーター
`expression`  
有効でないソース コード パラメーターの式を表す文字列。

`function_name`  
ハンドラーを呼び出した関数の名前。

`file_name`  
ハンドラーが呼び出されたソース コード ファイル。

`line_number`  
ハンドラーが呼び出されたソース コードの行番号。

`reserved`  
未使用。

## <a name="remarks"></a>コメント
有効でないパラメーターが C ランタイム ライブラリ関数に渡された場合、ライブラリ関数は、*無効なパラメーター ハンドラー*を呼び出します。これは、いくつかの作業のうちのいずれかを行うためにプログラマによって指定された関数です。 たとえば、問題をユーザーにレポートする、ログに書き込む、デバッガーで中断する、プログラムを終了する、または何も行わない、などです。 プログラマが何も関数も指定していない場合、既定のハンドラーである `_invoke_watson` が呼び出されます。

既定では、有効でないパラメーターがデバッグ コードで特定されると、CRT ライブラリ関数により、詳細パラメーターを使用して `_invalid_parameter` 関数が呼び出されます。 非デバッグ コードの場合は、`_invalid_parameter_noinfo` 関数が呼び出され、空のパラメーターを使用して `_invalid_parameter` 関数が呼び出されます。 非デバッグ CRT ライブラリ関数でプログラムの終了が必要な場合、`_invalid_parameter_noinfo_noreturn` 関数が呼び出され、空のパラメーターを使用して `_invalid_parameter` 関数を呼び出した後、プログラムを強制終了する `_invoke_watson` 関数を呼び出します。

`_invalid_parameter` 関数はユーザー定義の無効なパラメーター ハンドラーが設定されているかどうかを確認し、設定されている場合はそれを呼び出します。 たとえば、現在のスレッドで [set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義のスレッド ローカル ハンドラーが設定されている場合、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、[set_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義の無効なグローバル パラメーター ハンドラーが設定されているなら、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、既定のハンドラー `_invoke_watson` が呼び出されます。 `_invoke_watson` の既定の動作はプログラムを終了することです。 ユーザー定義のハンドラーは終了するか、戻るかのいずれかです。 確実に回復できるのでない限り、ユーザー定義のハンドラーでプログラムを終了することをお勧めします。 

既定のハンドラー `_invoke_watson` を呼び出す場合、プロセッサが [__fastfail](../../intrinsics/fastfail.md) 操作をサポートしているなら、これは `FAST_FAIL_INVALID_ARG` のパラメーターを使用して呼び出され、プロセスは終了します。 それ以外の場合、Fail Fast 例外が発生します。これは、アタッチされているデバッガーでキャッチできます。 プロセスが続行できる場合、`STATUS_INVALID_CRUNTIME_PARAMETER` の例外コード状態を使用して、Windows `TerminateProcess` 関数の呼び出しで終了します。 

## <a name="requirements"></a>要件  
|関数|必須ヘッダー|  
|--------------|------------------|  
|`_invalid_parameter`, `_invalid_parameter_noinfo`, `_invalid_parameter_noinfo_noreturn`, `_invoke_watson`|\<corecrt.h >|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)  
 [_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)  
 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)

