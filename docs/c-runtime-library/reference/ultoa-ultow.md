---
title: "_ultoa、_ultow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ultoa
- _ultow
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
- ultot
- ultow
- _ultoa
- _ultow
- _ultot
dev_langs:
- C++
helpviewer_keywords:
- ultot function
- converting integers
- _ultot function
- ultow function
- integers, converting
- _ultow function
- _ultoa function
- converting numbers, to strings
ms.assetid: 7a472dc4-5652-4513-93c3-3358522c23be
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 824e40d4c5879251fc029ad940b5fd6038fe4544
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="ultoa-ultow"></a>_ultoa、_ultow
符号なし長整数型を文字列に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_ultoa_s、_ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_ultoa(  
   unsigned long value,  
   char *str,  
   int radix   
);  
wchar_t *_ultow(  
   unsigned long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ultoa(  
   unsigned long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ultow(  
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
  
 `radix`  
 `value` の基数。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、`str` へのポインターを返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_ultoa` 関数は、`value` を null で終わる文字列に変換し、結果 (最大 33 バイト) を `str` に格納します。 オーバーフロー チェックは行われません。 `radix`基本型を指定`value`です。`radix` 2 ~ 36 の範囲内である必要があります。 `_ultow` 関数は、`_ultoa` 関数のワイド文字バージョンです。  
  
> [!IMPORTANT]
>  バッファー オーバーランを回避するには、`str` のバッファーを、変換された数字および末尾の null 文字を保持できるよう十分に大きくします。  
  
 C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ultoa`|\<stdlib.h>|  
|`_ultow`|\<stdlib.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)
