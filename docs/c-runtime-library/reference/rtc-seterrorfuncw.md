---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9c340310feb94ac181049c01d3ab1efaee2002c3
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
実行時エラー チェック (RTC) を報告するためのハンドラーとして関数を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `function`  
 実行時エラー チェックを処理する関数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 以前に定義されたエラー関数。または、以前に定義された関数がない場合は `NULL`。  
  
## <a name="remarks"></a>コメント  
 新しいコードでは `_RTC_SetErrorFuncW` のみを使用してください。 `_RTC_SetErrorFunc` は、下位互換性のためにのみライブラリに含まれています。  
  
 `_RTC_SetErrorFuncW` コールバックは、リンクされたコンポーネントにのみ適用され、グローバルには適用されません。  
  
 `_RTC_SetErrorFuncW` に渡すアドレスが有効なエラー処理関数のアドレスであることを確認してください。  
  
 かどうか、エラーが割り当てられて-1 の型を使用して[_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)、エラー処理関数は呼び出されません。  
  
 この関数を呼び出すには、まず、実行時エラー チェックの初期化関数の 1 つを呼び出す必要があります。 詳細については、「 [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)」を参照してください。  
  
 **_RTC_error_fnW** は次のように定義されています。  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  *linenumber* **, const wchar_t \*** `moduleName` **, const wchar_t \*** *format* **, ...);**  
  
 ここで、  
  
 `errorType`  
 [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)で指定したエラーの種類。  
  
 *ファイル名*  
 障害が発生したソース ファイル。または、使用できるデバッグ情報がない場合は null。  
  
 *行番号*  
 障害が発生した *ファイル名* 内の行番号。または、使用できるデバッグ情報がない場合は 0。  
  
 `moduleName`  
 この障害が発生した DLL 名または実行可能ファイル名。  
  
 *format*  
 残りのパラメーターを使用してエラー メッセージを表示するための printf スタイル文字列。 VA_ARGLIST の最初の引数は、発生した RTC エラーの番号です。  
  
 **_RTC_error_fnW** の使用例については、「[ネイティブ ランタイム チェックのカスタマイズ](/visualstudio/debugger/native-run-time-checks-customization)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [_CrtDbgReport、_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)
