---
title: "_ltoa、_ltow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ltoa
- _ltow
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
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs:
- C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25dc7c06f2e5eadacb568a096fda30f81a16570b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ltoa-ltow"></a>_ltoa、_ltow
長整数型を文字列に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_ltoa_s、_ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果の文字列。  
  
 `radix`  
 `value` の基数。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、`str` へのポインターを返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_ltoa` 関数は、`value` の数字を null で終わる文字列に変換し、結果 (最大 33 バイト) を `str` に格納します。 `radix`の基本型の引数を指定`value`2 ~ 36 の範囲にする必要があります。 場合`radix`10 に等しいと`value`は負の場合、格納されている文字列の最初の文字はマイナス記号 (-)。 `_ltow` は `_ltoa` のワイド文字バージョンです。`_ltow` の場合、2 番目の引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 これらの各関数は、Microsoft 固有です。  
  
> [!IMPORTANT]
>  バッファー オーバーランを回避するには、`str` のバッファーを、変換された数字、末尾の null 文字、および符号文字を保持できるよう十分に大きくします。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa、_ultow](../../c-runtime-library/reference/ultoa-ultow.md)