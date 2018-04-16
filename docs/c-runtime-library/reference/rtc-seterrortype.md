---
title: _RTC_SetErrorType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f6aaeaabe07f84a10167057ff94b45f91af0c93
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType
ランタイム エラー チェック (RTC) で検出されたエラーを特定の種類に関連付けます。 エラー ハンドラーは、指定した型のエラーを出力する方法を処理します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int _RTC_SetErrorType(  
   _RTC_ErrorNumber errnum,  
   int ErrType   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *errnum*  
 0 から [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)によって戻される値より 1 少ない値までの範囲の数値。  
  
 *ErrType*  
 この *errnum*に割り当てる値。 たとえば、 **_CRT_ERROR**を使用できます。 `_CrtDbgReport` をエラー ハンドラーとして使用している場合、 *ErrType* に指定できるのは、 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)で定義されたシンボルだけです。 独自のエラー ハンドラー ([_RTC_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)) がある場合、 *errnum*の数だけ *ErrType*を指定できます。  
  
 *ErrType* が _RTC_ERRTYPE_IGNORE の場合、 `_CrtSetReportMode`にとって特別な意味があるためエラーは無視されます。  
  
## <a name="return-value"></a>戻り値  
 エラーの種類 `type`の以前の値。  
  
## <a name="remarks"></a>コメント  
 既定では、すべてのエラーは *_CRT_ERROR* に対応する **ErrType**= 1 に設定されます。 既定のエラーの種類 ( **_CRT_ERROR**など) について詳しくは、 [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)をご覧ください。  
  
 この関数を呼び出すには、まず、実行時エラー チェックの初期化関数の 1 つを呼び出す必要があります。「[Using Run-Time Checks without the C Run-Time Library (C ランタイム ライブラリなしのランタイム チェックの使用)](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)」をご覧ください  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)