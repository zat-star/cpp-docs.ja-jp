---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
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
ms.openlocfilehash: 00098336be0198102b6154a7d6252b024b3cf949
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
実行時エラー チェック (RTC) の種類に関する簡単な説明を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *errnum*  
 0 から `_RTC_NumErrors`によって戻される値より 1 少ない値までの範囲の数値。  
  
## <a name="return-value"></a>戻り値  
 実行時エラー チェック システムによって検出されたエラーの 1 つの種類に関する簡単な説明が含まれている文字列。 エラーが 0 未満であるか、[_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md) によって返される値以上である場合、`_RTC_GetErrDesc` は NULL を返します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>関連項目  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)
