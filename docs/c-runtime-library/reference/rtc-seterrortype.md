---
title: _RTC_SetErrorType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _RTC_SetErrorType
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
apitype: DLLExport
f1_keywords:
- RTC_SetErrorType
- _RTC_SetErrorType
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9fcca983247f0f5e0c09899e7ebec2774ca92e6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType

ランタイム エラー チェック (RTC) で検出されたエラーを特定の種類に関連付けます。 エラー ハンドラーは、指定した型のエラーを出力する方法を処理します。

## <a name="syntax"></a>構文

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>パラメーター

*errnum*<br/>
0 から [_RTC_NumErrors](rtc-numerrors.md) によって戻される値より 1 少ない値までの範囲の数値。

*ErrType*<br/>
この *errnum*に割り当てる値。 たとえば、 **_CRT_ERROR**を使用できます。 使用している場合 **_CrtDbgReport**エラー ハンドラーとして*ErrType*で定義されたシンボルのいずれかを指定できますのみ[_CrtSetReportMode](crtsetreportmode.md)です。 独自のエラー ハンドラー ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)) がある場合、*errnum* の数だけ *ErrType* を指定できます。

*ErrType* _RTC_ERRTYPE_IGNORE の特別な意味を持つ **_CrtSetReportMode**;、エラーは無視されます。

## <a name="return-value"></a>戻り値

エラーの種類の以前の値*型*です。

## <a name="remarks"></a>コメント

既定では、すべてのエラーは *_CRT_ERROR* に対応する **ErrType**= 1 に設定されます。 既定のエラーの種類 (**_CRT_ERROR** など) について詳しくは、[_CrtDbgReport](crtdbgreport-crtdbgreportw.md) をご覧ください。

この関数を呼び出すには、まず、実行時エラー チェックの初期化関数の 1 つを呼び出す必要があります。「[Using Run-Time Checks without the C Run-Time Library (C ランタイム ライブラリなしのランタイム チェックの使用)](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)」をご覧ください

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h>|

詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)<br/>
