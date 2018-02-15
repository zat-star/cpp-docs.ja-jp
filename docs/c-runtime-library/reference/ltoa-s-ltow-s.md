---
title: "_ltoa_、_ltow_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ltoa_s
- _ltow_s
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
- _ltow_s
- _ltoa_s
- ltoa_s
- ltow_s
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa_s function
- ltow_s function
- long integer conversion to string
- converting numbers, to strings
- ltoa_s function
- _ltow_s function
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 181f03752a16f64329eb94ae0cd8fac091fa2987
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ltoas-ltows"></a>_ltoa_s、_ltow_s
長整数を文字列に変換します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_ltoa、_ltow](../../c-runtime-library/reference/ltoa-ltow.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果の文字列のバッファー。  
  
 `sizeOfstr`  
 `_ltoa_s` のバイトまたは `_ltow_s` のワードでの `str` のサイズ。  
  
 `radix`  
 `value` のベース。  
  
## <a name="return-value"></a>戻り値  
 関数が成功した場合はゼロ、そうでない場合はエラーコード。  
  
## <a name="remarks"></a>コメント  
 `_ltoa_s` 関数は、`value` の数字を null で終わる文字列に変換し、結果 (最大 33 バイト) を `str` に格納します。 `radix`の基本型の引数を指定`value`2 ~ 36 の範囲にする必要があります。 場合`radix`10 に等しいと`value`は負の場合、格納されている文字列の最初の文字はマイナス記号 (-)。 `_ltow_s` は、`_ltoa_s` のワイド文字バージョンであり、`_ltow_s` の 2 番目の引数はワイド文字列です。  
  
 `str` が `NULL` ポインターの場合、または `sizeOfstr` がゼロ以下の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は-1 を返して `errno` を `EINVAL` に設定し、`value` または `str` が長整数の範囲外である場合は、これらの関数は -1 を返して `errno` を `ERANGE` に設定します。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_ltoa_s`|\<stdlib.h>|  
|`_ltow_s`|\<stdlib.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa、_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ultoa_s、_ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)