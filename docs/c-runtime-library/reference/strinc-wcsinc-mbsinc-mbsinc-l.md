---
title: "_strinc、_wcsinc、_mbsinc、_mbsinc_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
dev_langs: C++
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fcda1d1c288e6fe8d6a3dfafea287e79ab6738f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc、_wcsinc、_mbsinc、_mbsinc_l
文字列ポインターを 1 文字進めます。  
  
> [!IMPORTANT]
>  `_mbsinc` および `_mbsinc_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_strinc(  
   const char *current,  
   _locale_t locale  
);  
wchar_t *_wcsinc(  
   const wchar_t *current,  
   _locale_t locale  
);  
unsigned char *_mbsinc(  
   const unsigned char *current   
);  
unsigned char *_mbsinc_l(  
   const unsigned char *current,  
   _locale_t locale  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `current`  
 文字ポインター。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの各ルーチンは、`current` の直後に続く文字へのポインターを返します。  
  
## <a name="remarks"></a>コメント  
 `_mbsinc` 関数は、`current` の直後に続くマルチバイト文字の最初のバイトへのポインターを返します。 `_mbsinc` は、現在使用中の[マルチバイト コード ページ](../../c-runtime-library/code-pages.md)に従ってマルチバイト文字シーケンスを認識します。`_mbsinc_l` は、渡されたロケール パラメーターを代わりに使用することを除いて同じものです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 Tchar.h に定義されている汎用テキスト関数 `_tcsinc` は、`_mbsinc` にマップされるか (`_MBCS` が定義されている場合)、または `_wcsinc` にマップされます (`_UNICODE` が定義されている場合)。 それ以外の場合、`_tcsinc` は `_strinc` に割り当てられます。 `_strinc` と `_wcsinc` はそれぞれ、`_mbsinc` の 1 バイト文字バージョンとワイド文字バージョンです。 `_strinc` と `_wcsinc` はこの割り当てにのみ使用し、それ以外には使用しないでください。 詳細については、「[Using Generic-Text Mappings](../../c-runtime-library/using-generic-text-mappings.md)」(汎用テキスト マップの使用) および「[Generic-Text Mappings](../../c-runtime-library/generic-text-mappings.md)」(汎用テキスト マップ) をご覧ください。  
  
 `current` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_mbsinc`|\<mbstring.h>|  
|`_mbsinc_l`|\<mbstring.h>|  
|`_strinc`|\<tchar.h>|  
|`_wcsinc`|\<tchar.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_strdec、_wcsdec、_mbsdec、_mbsdec_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [_strnextc、_wcsnextc、_mbsnextc、_mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [_strninc、_wcsninc、_mbsninc、_mbsninc_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)