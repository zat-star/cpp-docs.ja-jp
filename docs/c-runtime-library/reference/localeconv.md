---
title: localeconv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- localeconv
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
- localeconv
dev_langs:
- C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e93e21505a661deb470e4b31c8807ef5133a774
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="localeconv"></a>localeconv
ロケールの設定に関する詳細情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
struct lconv *localeconv( void );  
```  
  
## <a name="return-value"></a>戻り値  
 `localeconv` は、情報が埋め込まれた [struct lconv](../../c-runtime-library/standard-types.md) 型のオブジェクトを指すポインターを返します。 オブジェクトに含まれる値は、スレッド ローカル ストレージのロケール設定からコピーされ、後続の呼び出しによって上書きされること`localeconv`です。 このオブジェクトの値に加えられた変更は、ロケールの設定を変更しないでください。 `category` 値が `LC_ALL`、`LC_MONETARY`、`LC_NUMERIC` の [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 呼び出しで、構造体の内容が上書きされます。  
  
## <a name="remarks"></a>コメント  
 `localeconv` 関数は、現在のロケールにおける数値の書式設定に関する詳細情報を取得します。 この情報は型の構造体に格納`lconv`です。 `lconv`ロケールで定義された構造です。H には、次のメンバーが含まれています。  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 通貨でない数量の小数点文字。  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 通貨でない数量の小数点の左側にある数字のグループを区切る文字。  
  
 `char *grouping`  
 ポインター、 `char`-サイズが非金銭的数の数字の各グループのサイズを表す整数です。  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 現在のロケールの国際通貨記号。 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 現在のロケールの国内通貨記号。  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 通貨数量の小数点文字。  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 通貨数量の小数点の左側にある数字のグループを区切る文字。  
  
 `char *mon_grouping`  
 ポインター、 `char`-サイズが通貨書式の数字の各グループのサイズを表す整数です。  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 負でない通貨数量の符号を示す文字列。  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 負の通貨数量の符号を示す文字列。  
  
 `char int_frac_digits`  
 国際方式で書式化された通貨数量の小数点より右側の桁数。  
  
 `char frac_digits`  
 書式化された通貨数量の小数点より右側の桁数。  
  
 `char p_cs_precedes`  
 書式化された負でない通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。  
  
 `char p_sep_by_space`  
 書式化された負でない通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。  
  
 `char n_cs_precedes`  
 書式化された負の通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。  
  
 `char n_sep_by_space`  
 書式化された負の通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。  
  
 `char p_sign_posn`  
 書式化された負でない通貨数量での正符号の位置。  
  
 `char n_sign_posn`  
 書式化された負の通貨数量での正符号の位置。  
  
指定したメンバーの場合を除き、`lconv`構造を持つ`char *`と`wchar_t *`バージョンは、文字列へのポインター。 そのいずれかが `""` (または `wchar_t *` の場合は `L""`) に相当する場合は、長さがゼロか、現在のロケールでサポートされていないかのいずれかです。 `decimal_point` と `_W_decimal_point` は常にサポートされており、長さが 0 でないことにご注意ください。  
  
構造体の `char` メンバーは、文字ではなく、負でない小さな数です。 これらに相当する`CHAR_MAX`は、現在のロケールではサポートされていません。  
  
値`grouping`と`mon_grouping`は次の規則に従って解釈されます。  
  
- `CHAR_MAX` -どのさらにグループ化は行いません。  
  
- 0 - は、残りの各桁の直前の要素を使用します。  
  
- *n* -現在のグループを構成する数字の数。 次の要素が調べられて、現在のグループの前にある次のグループのサイズが決定されます。  
  
値は、`int_curr_symbol`は次の規則に従って解釈されます。  
  
-   最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。  
  
-   4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。  
  
値は、`p_cs_precedes`と`n_cs_precedes`は次の規則に従って解釈されます (、`n_cs_precedes`ルールは、かっこ内)。  
  
- 0 - 通貨記号には、負でない (負) 通貨値の値が次に示します。  
  
- 1-通貨記号では、負でない (負) 通貨値の前に付きます。  
  
値は、`p_sep_by_space`と`n_sep_by_space`は次の規則に従って解釈されます (、`n_sep_by_space`ルールは、かっこ内)。  
  
- 0 - 負でない (負) 通貨値をスペースで値から通貨記号が区切られます。  
  
- 1 - 通貨記号と負でない (負) 通貨値の領域の分離はありません。  
  
値は、`p_sign_posn`と`n_sign_posn`は次の規則に従って解釈されます。  
  
- 0 - 数値と通貨記号をかっこで囲みます。  
  
- 1-記号の文字列には、数値と通貨記号が前に付きます。  
  
- 2-記号の文字列には、数値と通貨記号が次に示します。  
  
- 3-記号の文字列には、通貨記号が前に記述します。  
  
- 4-すぐに次のように通貨記号の記号文字列します。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`localeconv`|\<locale.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="see-also"></a>参照  
 [ロケール](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll 関数](../../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)