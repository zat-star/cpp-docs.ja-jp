---
title: "localeconv | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "localeconv"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "localeconv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "lconv 型"
  - "localeconv 関数"
  - "ロケール, 取得 (情報を)"
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# localeconv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ロケールの設定に関する詳細情報を取得します。  
  
## 構文  
  
```  
  
struct lconv *localeconv( void );  
```  
  
## 戻り値  
 `localeconv` は、結果が書き込まれた [struct lconv](../../c-runtime-library/standard-types.md) 型のオブジェクトへのポインターを返します。  オブジェクトに含まれる値は、`localeconv` 関数への以降の呼び出しによって上書きされることがあるため、このオブジェクトは直接変更しないでください。  `category` 値を `LC_ALL`、`LC_MONETARY`、または `LC_NUMERIC` のいずれかに指定して [setlocale](../Topic/setlocale,%20_wsetlocale.md) 関数を呼び出すと、構造体の内容が上書きされます。  
  
## 解説  
 `localeconv` 関数は、現在のロケールの数値書式に関する詳細情報を取得します。  この情報は、**lconv** 型の構造体に格納されます。  **lconv** 構造体は、LOCALE.H で定義され、次のメンバーから構成されます。  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 通貨以外の数値書式で使用する小数点文字。  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 通貨以外の数値書式における整数部の数字のグループを区切る文字。  
  
 `char *grouping`  
 通貨以外の数値書式における数字の各グループの桁数。  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 現在のロケールにおける国際通貨記号。  最初の 3 文字には、*ISO 4217 \(Codes for the Representation of Currency and Funds\)* 規格に定義されている英字の国際通貨記号を指定します。  4 番目の文字 \(NULL 文字の直前にある文字\) は、国際通貨記号と通貨値を区切るために使用します。  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 現在のロケールの現地通貨記号。  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 通貨書式で使用する小数点文字。  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 通貨書式における整数部の数字のグループを区切る文字。  
  
 `char *mon_grouping`  
 通貨書式における数字の各グループの桁数。  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 負でない通貨値の符号を示す文字列。  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 負の通貨値の符号を表す文字列。  
  
 `char int_frac_digits`  
 国際的な通貨書式の小数部の桁数。  
  
 `char frac_digits`  
 通貨書式の小数部の桁数。  
  
 `char p_cs_precedes`  
 通貨記号が、負でない通貨値の前にある場合は 1 に設定します。  通貨記号が値の後ろにある場合は 0 に設定します。  
  
 `char p_sep_by_space`  
 通貨記号と負でない通貨値が空白で区切られている場合は 1 に設定します。  空白で区切られていない場合は 0 に設定します。  
  
 `char n_cs_precedes`  
 通貨記号が、負の通貨値の前にある場合は 1 に設定します。  通貨記号が値の後ろにある場合は 0 に設定します。  
  
 `char n_sep_by_space`  
 通貨記号と負の通貨値が空白で区切られている場合は 1 に設定します。  空白で区切られていない場合は 0 に設定します。  
  
 `char p_sign_posn`  
 負でない通貨書式の符号の位置。  
  
 `char n_sign_posn`  
 負の通貨書式の符号の位置。  
  
 `char` `*` と `wchar_t *` の各バージョンがある構造体のメンバーは、文字列へのポインターです。  これらが `""` \(または `wchar_t *` の `L""`\) に等しい場合、該当する情報の長さがゼロであるか、または現在のロケールでサポートされていません。  `decimal_point` と `_W_decimal_point` は常にサポートされ、ゼロでない長さになります。  
  
 構造体の `char` 型メンバーの値は文字ではなく、負でない小さい数値です。  このうち、**CHAR\_MAX** と等しいメンバーは現在のロケールでサポートされていません。  
  
 **grouping** および **mon\_grouping** の要素は、次の規則に従って解釈されます。  
  
 **CHAR\_MAX**  
 これ以上のグループ化は行いません。  
  
 0  
 残りの各桁に直前の要素を使用します。  
  
 *n*  
 現在のグループを構成する桁数を示します。  現在のグループの前に次の要素を調べ、次のグループの桁数を判定します。  
  
 **int\_curr\_symbol** の値は、次の規則に従って解釈されます。  
  
-   最初の 3 文字では、ISO 4217 \(Codes for the Representation of Currency and Funds\) 規格で定義されている英字の国際通貨記号を指定します。  
  
-   4 番目の文字 \(NULL 文字の直前にある文字\) は、国際通貨記号と通貨値を区切るために使用します。  
  
 **p\_cs\_precedes** および **n\_cs\_precedes** の値は、次の規則に従って解釈されます \(かっこ内は **n\_cs\_precedes**\)。  
  
 0  
 通貨記号が、負でない \(負の\) 通貨値の後ろにあります。  
  
 1  
 通貨記号が、負でない \(負の\) 通貨値の前にあります。  
  
 **p\_sep\_by\_space** および **n\_sep\_by\_space** の値は、次の規則に従って解釈されます \(かっこ内は **n\_sep\_by\_space**\)。  
  
 0  
 通貨記号と負でない \(負の\) 通貨値を空白で区切ります。  
  
 1  
 通貨記号と負でない \(負の\) 通貨値を空白で区切りません。  
  
 **p\_sign\_posn** および **n\_sign\_posn** の値は、次の規則に従って解釈されます。  
  
 0  
 数値と通貨記号をかっこで囲みます。  
  
 1  
 符号文字列が数値と通貨記号の前にあります。  
  
 2  
 符号文字列が数値と通貨記号の後ろにあります。  
  
 3  
 符号文字列が通貨記号の直前にあります。  
  
 4  
 符号文字列が通貨記号の直後にあります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`localeconv`|\<locale.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 参照  
 [ロケール](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、\_strftime\_l、\_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)