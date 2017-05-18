---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_SetErrorFunc
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
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs:
- C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: 13
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f5846074abafcbbb3cfe55cca00b9912dd0a994e
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc
実行時エラー チェック (RTC) を報告するためのハンドラーとして関数を指定します。 この関数は使用されなくなりました。代わりに `_RTC_SetErrorFuncW` をご使用ください。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn function   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *関数*  
 実行時エラー チェックを処理する関数のアドレス。  
  
## <a name="return-value"></a>戻り値  
 以前に定義されたエラーの関数。 以前に定義された関数がない場合は、NULL が返されます。  
  
## <a name="remarks"></a>コメント  
 この関数は使用しないでください。代わりに `_RTC_SetErrorFuncW`をご使用ください。 これは下位互換性のためだけに残されています。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [_CrtDbgReport、_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)
