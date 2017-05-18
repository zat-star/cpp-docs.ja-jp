---
title: "_mbsnbicmp、_mbsnbicmp_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3eff360605f782a2a159195a91dfc3d97da2cb8a
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp、_mbsnbicmp_l
2 個のマルチバイト文字列の `n` のバイトを、大文字と小文字を無視して比較します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `string1, string2`  
 Null で終わる比較対象の文字列。  
  
 `count`  
 比較するバイト数。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、部分文字列間の関係を示しています。  
  
|戻り値|説明|  
|------------------|-----------------|  
|< 0|`string1` の部分文字列が `string2` の部分文字列より小さい。|  
|0|`string1` の部分文字列は `string2` の部分文字列と同じ。|  
|> 0|`string1` の部分文字列が `string2` の部分文字列より大きい。|  
  
 エラーが発生した場合、`_mbsnbcmp` は `_NLSCMPERROR` を返します。これは、String.h および Mbstring.h で定義されています。  
  
## <a name="remarks"></a>コメント  
 `_mbsnbicmp` 関数は、`count` と `string1` の先頭の最大 `string2` バイトで序数に基づく比較を実行します。 各文字を小文字に変換することで比較を実行します。`_mbsnbcmp` は `_mbsnbicmp` の大文字小文字を区別するバージョンです。 `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達すると比較は終了します。 `count` 文字を比較する前に、どちらかの文字列で終端の NULL 文字に到達したときに、文字列が等しい場合は短いほうの文字列が小さくなります。  
  
 `_mbsnbicmp` は `_mbsnicmp` に似ていますが、文字ではなく、最大 `count` バイトの文字列を比較する点が異なります。  
  
 ASCII の表の 'Z' と 'a' の間にある文字 ('['、'\\'、']'、'^'、'_'、'\`') を含む 2 つの文字列は、場合に応じて異なる方法で比較します。 たとえば、2 つの文字列 "`ABCDE`" および "`ABCD^`" を比較する場合、小文字で比較する場合 ("`abcde`" > "`abcd^`") と、大文字で比較する場合 ("`ABCDE`" < "`ABCD^`") で方法が異なります。  
  
 `_mbsnbicmp` 関数は、現在使用中の[マルチバイト コード ページ](../../c-runtime-library/code-pages.md)に基づいて、マルチバイト文字列を認識します。 これは、現在のロケール設定の影響を受けません。  
  
 `string1` または `string2` が Null ポインターの場合、`_mbsnbicmp` は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_mbsnbicmp`|<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[_mbsnbcmp、_mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)」の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat、_mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp、_mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)
