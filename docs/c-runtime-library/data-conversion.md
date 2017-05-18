---
title: "データ変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.conversions
dev_langs:
- C++
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
caps.latest.revision: 12
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 11971f357250d56f8b474595a9608dc1ea0b478d
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="data-conversion"></a>データ変換
これらのルーチンは、ある形式から別の形式にデータを変換します。 通常、これらのルーチンは、ユーザーが作成した変換より速く変換を実行します。 `to` プレフィックスで始まるルーチンは、それぞれ、関数およびマクロとして実装されます。 実装の使い分けについては、「[関数またはマクロの選択に関する推奨事項](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照してください。  
  
### <a name="data-conversion-routines"></a>データ変換ルーチン  
  
|ルーチン|用途|  
|-------------|---------|  
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|整数の絶対値を求める|  
|[atof、_atof_l、_wtof、_wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|文字列を `float` に変換する|  
|[atoi、_atoi_l、_wtoi、_wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|文字列を `int` に変換する|  
|[_atoi64、_atoi64_l、_wtoi64、_wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|文字列を `__int64` に変換する|  
|[atol、_atol_l、_wtol、_wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|文字列を `long` に変換する|  
|[_ecvt](../c-runtime-library/reference/ecvt.md)、[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|`double` を指定された長さの文字列に変換する|  
|[_fcvt](../c-runtime-library/reference/fcvt.md)、[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|`double` を小数点の以下が指定された桁数である文字列に変換する|  
|[_gcvt](../c-runtime-library/reference/gcvt.md)、[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|`double` 数を文字列に変換する。文字列をバッファーに格納する|  
|[_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)、[_itoa_s、_i64toa_s、_ui64toa_s、_itow_s、_i64tow_s、_ui64tow_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|`int`、または `__int64` を文字列に変換する|  
|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|`long` 整数の絶対値を求める|  
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|`long long` 整数の絶対値を求める|  
|[_ltoa、_ltow](../c-runtime-library/reference/ltoa-ltow.md)、[_ltoa_s、_ltow_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|`long` を文字列に変換する|  
|[_mbbtombc、_mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1 バイト マルチバイト文字を、対応する 2 バイト マルチバイト文字に変換する|  
|[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|日本工業標準 (JIS: Japan Industry Standard) 文字を Japan Microsoft (JMS) 文字に変換する|  
|[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JMS 文字を JIS 文字に変換する|  
|[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|マルチバイト文字を 1 バイトのひらがなコードに変換する|  
|[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|マルチバイト文字を 1 バイト カタカナ コードに変換する|  
|[_mbctombb、_mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2 バイト マルチバイト文字を、対応する 1 バイト マルチバイト文字に変換する|  
|[mbstowcs、_mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)、[mbstowcs_s、_mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換|  
|[mbtowc、_mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|マルチバイト文字を対応するワイド文字に変換|  
|[strtod、_strtod_l、wcstod、_wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|文字列を `double` に変換する|  
|[strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|文字列を `long` 整数に変換する|  
|[strtoul、_strtoul_l、wcstoul、_wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|文字列を `unsigned long` 整数に変換する|  
|[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|ロケール固有の情報に基づいて、文字列を照合形式に変換します。|  
|[toascii、__toascii](../c-runtime-library/reference/toascii-toascii.md)|文字を ASCII コードに変換する||  
|[tolower、_tolower、towlower、_tolower_l、_towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)、[_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在大文字の場合は小文字に変換する|  
|[tolower、_tolower、towlower、_tolower_l、_towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|文字を無条件に小文字に変換する|[System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|  
|[toupper、_toupper、towupper、_toupper_l、_towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)、[_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在小文字の場合は大文字に変換する|  
|[toupper、_toupper、towupper、_toupper_l、_towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|文字を無条件に大文字に変換する|  
|[_ultoa、_ultow](../c-runtime-library/reference/ultoa-ultow.md)、[_ultoa_s、_ultow_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|`unsigned long` を文字列に変換する|  
|[wcstombs、_wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md)、[wcstombs_s、_wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換する|  
|[wctomb、_wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md)、[wctomb_s、_wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|ワイド文字を対応するマルチバイト文字に変換する|  
|[atof、_atof_l、_wtof、_wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|ワイド文字列を `double` に変換する|   
|[atoi、_atoi_l、_wtoi、_wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|ワイド文字列を `int` に変換する|  
|[_atoi64、_atoi64_l、_wtoi64、_wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|ワイド文字列を `__int64` に変換する|  
|[atol、_atol_l、_wtol、_wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|ワイド文字列を `long` に変換する|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
