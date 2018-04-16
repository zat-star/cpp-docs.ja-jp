---
title: "strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0545fd71f571caa2fbb12cefb010c274cbda9f28
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l
ロケール固有の情報に基づいて文字列を変換します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strDest`  
 対象文字列。  
  
 `strSource`  
 ソース文字列。  
  
 `count`  
 配置する文字の最大数`strDest`です。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 変換された文字列の長さを返します。終端の null 文字は含まれません。 戻り値が `count` 以上である場合、`strDest` のコンテンツは予測できません。 エラーの場合、各関数は `errno` を設定し、`INT_MAX` を返します。 無効な文字の場合、`errno` は `EILSEQ` に設定されます。  
  
## <a name="remarks"></a>コメント  
 `strxfrm` 関数は、`strSource` によって指されている文字列を、`strDest` に格納されている新しい照合フォームに変換します。 null 文字を含めて `count` 以内の文字が変換され、結果の文字列に配置されます。 変換は、ロケールの `LC_COLLATE` カテゴリ設定を使用して行われます。 `LC_COLLATE` の詳細については、[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) に関する記事をご覧ください。 `strxfrm` は、ロケールに依存する動作に現在のロケールを使用します。`_strxfrm_l` は、現在のロケールの代わりに渡されたロケールを使用することを除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 変換後、変換された 2 つの文字列を使用した `strcmp` への呼び出しにより、元の 2 つの文字列に適用された `strcoll` への呼び出しと同じ結果が得られます。 `strcoll` と `stricoll` と同様に、`strxfrm` はマルチバイト文字の文字列を必要に応じて自動的に処理します。  
  
 `wcsxfrm` は `strxfrm` のワイド文字バージョンで、`wcsxfrm` の文字列引数はワイド文字ポインターです。 `wcsxfrm` の場合、文字列変換の後、変換された 2 つの文字列を使用した `wcscmp` への呼び出しにより、元の 2 つの文字列に適用された `wcscoll` への呼び出しと同じ結果が得られます。 それ以外では、`wcsxfrm` と `strxfrm` の動作は同じです。 `wcsxfrm` は、ロケールに依存する動作に現在のロケールを使用します。`_wcsxfrm_l` は、現在のロケールの代わりに渡されたロケールを使用します。  
  
 これらの関数では、パラメーターの検証が行われます。 `strSource` が Null ポインターの場合、`strDest` が NULL ポインター (カウントがゼロでない場合) の場合、または `count` が `INT_MAX` を超える場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`INT_MAX` を返します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 "C" ロケールでは、文字セット (ASCII 文字セット) 内の文字の順序は、辞書式文字順序と同じです。 ただし、その他のロケールでは、文字セット内の文字の順序が辞書式文字順序と異なる場合があります。 たとえば、ヨーロッパの一部のロケールで文字 'a' (値 0x61) の前に、文字 ' &\#x00E4;'(値 0xE4)、文字セットが、文字 'ä' の前に、文字 'a' 辞書。  
  
 文字セットと辞書式文字順序が異なるロケールで、元の文字列で `strxfrm` を使用し、結果の文字列で `strcmp` を使用して、現在のロケールの `LC_COLLATE` カテゴリの設定に従って辞書式文字列比較を生成します。 このように、上記のロケールで 2 つの文字列を辞書式に比較するには、元の文字列で `strxfrm` を使用し、結果の文字列で `strcmp` を使用します。 または、元の文字列で `strcmp` ではなく `strcoll` を使用することもできます。  
  
 `strxfrm` は基本的に、`LCMAP_SORTKEY` を持つ [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) のラッパーです。  
  
 次の式の値は、ソース文字列の `strxfrm` 変換を保持するために必要な配列のサイズです。  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 "C" ロケールでのみ、`strxfrm` は次のものと同等です。  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`strxfrm`|\<string.h>|  
|`wcsxfrm`|\<string.h> または \<wchar.h>|  
|`_strxfrm_l`|\<string.h>|  
|`_wcsxfrm_l`|\<string.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 関数](../../c-runtime-library/strcoll-functions.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)