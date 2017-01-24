---
title: "ロケール | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "国別情報"
  - "言語情報ルーチン"
  - "ロケール ルーチン"
  - "ローカリゼーション, ロケール"
  - "setlocale 関数"
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ロケール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*ロケール*とは、プログラムをカスタマイズするために使用できる国または地域と言語を表します。  ロケールに依存するカテゴリとしては、日付や通貨の値の表示形式などがあります。  詳細については、「[ロケールのカテゴリ](../c-runtime-library/locale-categories.md)」を参照してください。  
  
 現在のプログラムまたはスレッドのロケール情報の一部またはすべてを変更または照会するには、[setlocale](../Topic/setlocale,%20_wsetlocale.md) 関数を `_l` のサフィックスなしで使用します。  `_l` サフィックス付きの関数を指定すると、特定の関数の実行中にのみ渡されたロケール パラメーターをロケール情報として使用します。  `_l` サフィックス付きの関数を使用する場合のロケールを作成するには、[\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) を使用します。  このロケールを解放するには、[\_free\_locale](../c-runtime-library/reference/free-locale.md) を使用します。  現在のロケールを取得するには、[\_get\_current\_locale](../Topic/_get_current_locale.md) を使用します。  
  
 各スレッドで独自のロケールを設定するか、プログラム内のすべてのスレッドで同じロケールを共有するかどうかを制御するには、[\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) を使用します。  詳細については、「[Locales and Code Pages \(ロケールとコード ページ\)](../text/locales-and-code-pages.md)」を参照してください。  
  
 次の表に示す関数のセキュリティを強化したバージョンは、`_s` \("secure"\) というサフィックスによって表されます。  詳細については、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」を参照してください。  
  
### ロケールに依存するルーチン  
  
|ルーチン|使用方法|`setlocale` カテゴリの設定の依存関係|  
|----------|----------|------------------------------|  
|[atof、\_atof\_l、\_wtof、\_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|文字を浮動小数点型の値に変換|`LC_NUMERIC`|  
|[atoi、\_atoi\_l、\_wtoi、\_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|文字を整数型の値に変換|`LC_NUMERIC`|  
|[\_atoi64、\_atoi64\_l、\_wtoi64、\_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|文字を 64 ビットの整数型の値に変換|`LC_NUMERIC`|  
|[atol、\_atol\_l、\_wtol、\_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|文字を long 型の値に変換|`LC_NUMERIC`|  
|[\_atodbl、\_atodbl\_l、\_atoldbl、\_atoldbl\_l、\_atoflt、\_atoflt\_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|文字を double\-long 型の値に変換|`LC_NUMERIC`|  
|[is ルーチン](../c-runtime-library/is-isw-routines.md)|特定の状態で指定した整数をテストします。|`LC_CTYPE`|  
|[isleadbyte、\_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|先行バイトのテスト|`LC_CTYPE`|  
|[localeconv](../c-runtime-library/reference/localeconv.md)|数量を書式設定するために適切な値を読み取る|`LC_MONETARY, LC_NUMERIC`|  
|[MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)|現在のロケールのマルチバイト文字の最大長さのバイト数 \(STDLIB.H で定義されているマクロ\)|`LC_CTYPE`|  
|[\_mbccpy、\_mbccpy\_l](../Topic/_mbccpy,%20_mbccpy_l.md),[\_mbccpy\_s、\_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|マルチバイト文字の 1 文字をコピー|`LC_CTYPE`|  
|[\_mbclen、mblen、\_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|マルチバイト文字のバイト数を検証して返す|`LC_CTYPE`|  
|[strlen、wcslen、\_mbslen、\_mbslen\_l、\_mbstrlen、\_mbstrlen\_l](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)|マルチバイト文字列の場合、文字列内の各文字を検証し、文字列の長さを返す|`LC_CTYPE`|  
|[mbstowcs、\_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs\_s、\_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換|`LC_CTYPE`|  
|[mbtowc、\_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)|マルチバイト文字を対応するワイド文字に変換|`LC_CTYPE`|  
|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 関数|書式付き出力を書き出す|`LC_NUMERIC` \(小数点文字の出力を決定\)|  
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) 関数|書式付き入力を読み取る|`LC_NUMERIC` \(基数文字が認識されます\)|  
|[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)|プログラムのロケールを選択する|該当なし|  
|[strcoll、wcscoll、\_mbscoll、\_strcoll\_l、\_wcscoll\_l、\_mbscoll\_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|2 つの文字列の文字を比較する|`LC_COLLATE`|  
|[\_stricmp、\_wcsicmp、\_mbsicmp、\_stricmp\_l、\_wcsicmp\_l、\_mbsicmp\_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|大文字小文字に関係なく、2 つの文字列を比較する|`LC_CTYPE`|  
|[\_stricoll、\_wcsicoll、\_mbsicoll、\_stricoll\_l、\_wcsicoll\_l、\_mbsicoll\_l](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|2 つの文字列の文字を比較する \(大文字小文字を区別しない\)|`LC_COLLATE`|  
|[\_strncoll、\_wcsncoll、\_mbsncoll、\_strncoll\_l、\_wcsncoll\_l、\_mbsncoll\_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|2 つの文字列の先頭の `n` 文字を比較する|`LC_COLLATE`|  
|[\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|大文字小文字に関係なく、2 つの文字列の文字を比較する。|`LC_CTYPE`|  
|[\_strnicoll、\_wcsnicoll、\_mbsnicoll、\_strnicoll\_l、\_wcsnicoll\_l、\_mbsnicoll\_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|2 つの文字列の先頭の `n` 文字を比較する \(大文字小文字を区別しない\)|`LC_COLLATE`|  
|[strftime、wcsftime、\_strftime\_l、\_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|指定された `format` 引数に従って日付と時刻の値を書式設定する|`LC_TIME`|  
|[\_strlwr、\_wcslwr、\_mbslwr、\_strlwr\_l、\_wcslwr\_l、\_mbslwr\_l](../Topic/_strlwr,%20_wcslwr,%20_mbslwr,%20_strlwr_l,%20_wcslwr_l,%20_mbslwr_l.md),[\_strlwr\_s、\_strlwr\_s\_l、\_mbslwr\_s、\_mbslwr\_s\_l、\_wcslwr\_s、\_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|指定した文字列内の大文字をその位置で小文字に変換する|`LC_CTYPE`|  
|[strtod、\_strtod\_l、wcstod、\_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|文字列を `double` 型の値に変換する|`LC_NUMERIC` \(基数文字が認識されます\)|  
|[strtol、wcstol、\_strtol\_l、\_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|`long` 値に変換する文字列|`LC_NUMERIC` \(基数文字が認識されます\)|  
|[strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|文字列を unsigned long 型の値に変換する|`LC_NUMERIC` \(基数文字が認識されます\)|  
|[\_strupr、\_strupr\_l、\_mbsupr、\_mbsupr\_l、\_wcsupr\_l、\_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[\_strupr\_s、\_strupr\_s\_l、\_mbsupr\_s、\_mbsupr\_s\_l、\_wcsupr\_s、\_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|文字列内の小文字をその位置で大文字に変換する|`LC_CTYPE`|  
|[strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|ロケールに従って文字列を照合形式に変換する|`LC_COLLATE`|  
|[tolower、\_tolower、towlower、\_tolower\_l、\_towlower\_l](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md),[\_mbctolower、\_mbctolower\_l、\_mbctoupper、\_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|指定した文字を対応する小文字に変換する|`LC_CTYPE`|  
|[toupper、\_toupper、towupper、\_toupper\_l、\_towupper\_l](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md),[\_mbctolower、\_mbctolower\_l、\_mbctoupper、\_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|指定した文字を対応する大文字に変換する|`LC_CTYPE`|  
|[wcstombs、\_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md),[wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換する|`LC_CTYPE`|  
|[wctomb、\_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb\_s、\_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|ワイド文字を対応するマルチバイト文字に変換する|`LC_CTYPE`|  
  
> [!NOTE]
>  マルチバイトのルーチンの場合、マルチバイトのコード ページは [setlocale](../Topic/setlocale,%20_wsetlocale.md) で設定されたロケールと同じである必要があります。  `_MB_CP_LOCALE` 引数を指定した [\_setmbcp](../c-runtime-library/reference/setmbcp.md) では、マルチバイトのコード ページを `setlocale` のコード ページと同じにします。  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)