---
title: "_ltoa、_ltow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ac9a6808371183a234f5cd61312f641e6ea9e49f
ms.lasthandoff: 02/24/2017

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
 `_ltoa` 関数は、`value` の数字を null で終わる文字列に変換し、結果 (最大 33 バイト) を `str` に格納します。 `radix` 引数は `value` の基数を指定します。2 から 36 の範囲内である必要があります。 `radix` が 10 で、`value` が負の場合は、保存される文字列の最初の文字は負符号 (–) になります。 `_ltow` は `_ltoa` のワイド文字バージョンです。`_ltow` の場合、2 番目の引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 これらの各関数は、Microsoft 固有です。  
  
> [!IMPORTANT]
>  バッファー オーバーランを回避するには、`str` のバッファーを、変換された数字、末尾の null 文字、および符号文字を保持できるよう十分に大きくします。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h>|  
|`_ltow`|\<stdlib.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) の例を参照してください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa、_ultow](../../c-runtime-library/reference/ultoa-ultow.md)
