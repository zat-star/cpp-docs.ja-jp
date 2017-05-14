---
title: "_ultoa_s、_ultow_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ultow_s
- _ultoa_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ultow_s
- ultoa_s
- ultow_s
- _ultoa_s
dev_langs:
- C++
helpviewer_keywords:
- _ultoa_s function
- converting integers
- integers, converting
- _ultow_s function
- ultoa_s function
- converting numbers, to strings
- ultow_s function
ms.assetid: 606ce905-6752-46ac-a15a-bdc22920e1d4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: f35701cf1ef644b140cae01ef2d8707cfb387a68
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="ultoas-ultows"></a>_ultoa_s、_ultow_s
符号なし長整数を文字列に変換します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_ultoa、_ultow](../../c-runtime-library/reference/ultoa-ultow.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _ultoa_s(  
    unsigned long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ultoa_s(  
    unsigned long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果の文字列。  
  
 `sizeOfstr`  
 `_ultoa_s` のバイトまたは `_ultow_s` のワードでの `str` のサイズ。  
  
 `radix`  
 `value` のベース。  
  
## <a name="return-value"></a>戻り値  
 関数が成功した場合はゼロ、そうでない場合はエラーコード。  
  
## <a name="remarks"></a>コメント  
 `_ultoa_s` 関数は、`value` の数字を null で終わる文字列に変換し、結果 (最大 33 バイト) を `str` に格納します。 `radix`の基本型の引数を指定`value`2 ~ 36 の範囲にする必要があります。 `_ultow_s` は、`_ultoa_s` のワイド文字バージョンであり、`_ultow_s` の 2 番目の引数はワイド文字列です。  
  
 `str` が `NULL` ポインターである場合、または `sizeOfstr` がゼロ以下の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返して `errno` を `EINVAL` に設定し、`value` または `str` が長整数の範囲外である場合は、これらの関数は -1 を返して `errno` を `ERANGE` に設定します。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ultot_s`|`_ultoa_s`|`_ultoa_s`|`_ultow_s`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ultoa_s`|\<stdlib.h>|  
|`_ultow_s`|\<stdlib.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_ultoa、_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ltoa、_ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [_ltoa_s、_ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [_ltoa_s、_ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)
