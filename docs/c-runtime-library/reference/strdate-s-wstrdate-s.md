---
title: "_strdate_s、_wstrdate_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdate_s
- _wstrdate_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
dev_langs: C++
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71117aed66d83c2c2ae1651c4de9c91e06a43653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strdates-wstrdates"></a>_strdate_s、_wstrdate_s
現在のシステム日付をバッファーにコピーします。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_strdate、_wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 書式設定された日付文字列が格納されるバッファーへのポインター。  
  
 [入力] `numberOfElements`  
 バッファーのサイズ。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは ERRNO.H で定義されます。この関数によって生成される正確なエラーについては、下記の表をご覧ください。 エラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」をご覧ください。  
  
## <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`numberOfElements`|Return|`buffer` の内容|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|(任意)|`EINVAL`|変更されない|  
|`NULL` ではない (有効なバッファーを指す)|0|`EINVAL`|変更されない|  
|`NULL` ではない (有効なバッファーを指す)|0 < `numberOfElements` < 9|`EINVAL`|空の文字列|  
|`NULL` ではない (有効なバッファーを指す)|`numberOfElements` >= 9|0|コメントで指定されている書式設定の、現在の日付|  
  
## <a name="security-issues"></a>セキュリティ上の問題  
 `numberOfElements` パラメーターが 9 よりも大きい場合、バッファーに無効な非 `NULL` 値を渡すとアクセス違反になります。  
  
 `buffer` の実際のサイズより大きいサイズの値を渡すと、バッファー オーバーランが発生します。  
  
## <a name="remarks"></a>コメント  
 これらの関数には、セキュリティを強化したバージョンとして `_strdate` および `_wstrdate` があります。 `_strdate_s` 関数は、現在のシステム日付を `buffer` が指すバッファーに `mm`/`dd`/`yy` の書式設定でコピーします。`mm` は月を表す 2 桁、`dd` は日を表す 2 桁、`yy` は西暦年の下 2 桁です。 たとえば、文字列 `12/05/99` は、1999 年 12 月 5 日を表します。 バッファーの長さは 9 文字以上でなければなりません。  
  
 ワイド文字を扱う場合は、`_wstrdate_s` ではなく `_strdate_s` を使用します。`_wstrdate_s` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 それ以外では、これらの関数の動作は同じです。  
  
 `buffer` が `NULL` ポインターである場合、または `numberOfElements` が 9 文字未満の場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返し、バッファーが `NULL` である、または `numberOfElements` が 0 以下である場合に `errno` を `EINVAL` に設定します。あるいは、`numberOfElements` が 9 より小さい場合、`errno` を `ERANGE` に設定します。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_strdate`|\<time.h>|  
|`_wstrdate`|\<time.h> または \<wchar.h>|  
|`_strdate_s`|\<time.h>|  
  
## <a name="example"></a>例  
 [time](../../c-runtime-library/reference/time-time32-time64.md) の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、_mktime32、_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)