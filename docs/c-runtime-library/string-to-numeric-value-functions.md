---
title: "文字列を数値に変換する関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstoui64"
  - "_tcstoi64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "解析, 数値文字列"
  - "文字列変換, 数値への"
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 文字列を数値に変換する関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

-   [strtod、\_strtod\_l、wcstod、\_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)  
  
-   [strtol、wcstol、\_strtol\_l、\_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)  
  
-   [strtoul、\_strtoul\_l、wcstoul、\_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)  
  
-   [\_strtoi64、\_wcstoi64、\_strtoi64\_l、\_wcstoi64\_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)  
  
-   [\_strtoui64、\_wcstoui64、\_strtoui64\_l、\_wcstoui64\_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)  
  
## 解説  
 **strtod** ファミリの各関数は、null で終わる文字列を数値に変換します。  使用できる機能を次の表に示します。  
  
|関数|説明|  
|--------|--------|  
|`strtod`|倍精度浮動小数点値に変換する文字列|  
|`strtol`|長整数に変換する文字列|  
|`strtoul`|unsigned long 型の整数に変換する文字列|  
|`_strtoi64`|`__int64` の 64 ビット整数に変換する文字列|  
|`_strtoui64`|`__int64` の符号なしな 64 ビット整数に変換する文字列|  
  
 `wcstod`、`wcstol`、`wcstoul`と `_wcstoi64` は `strtod`、`strtol`、`strtoul`と `_strtoi64`のワイド文字バージョンであり、それぞれです。  これらのワイド文字単位の各関数の文字列引数はワイド文字列で、; 各関数は single\-byte–character の対応とは別の方法で同様に動作します。  
  
 `strtod` 関数は 2 個の引数を受け取ります。: 1 番目の変換プロセスの最後の文字を入力文字列と 2 番目のポインターです。  `strtol`、`strtoul`、**\_strtoi64** と **\_strtoui64** は基数として変換プロセスで使用する 3 番目の引数を受け取ります。  
  
 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。  各関数は、数値の一部として認識できない最初の文字から文字列を読み取ることを停止します。  数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。  `strtol`、`strtoul`、`_strtoi64`と `_strtoui64`の場合、この終端文字は、大きい最初の数字ユーザー指定の基数に以上であるでもかまいません。  
  
 変換終了文字へのユーザー指定のポインターがコール タイムの **NULL** に設定し、スキャンを停止した文字へのポインターは、代わりに格納されます。  変換 \(有効な数字が見つからなかった場合、または無効なベースが指定されました\) 実行できない場合は、文字列ポインターの値は、そのアドレスに格納されます。  
  
 `strtod` のフォームは、次の文字列を想定する:  
  
 *null*\[\] \[\]*\)* `digits`\[\] \[\] \#\#\#.`digits`\[{**d** &#124; **D** &#124; **e** &#124; **E**} \[\]*\)* `digits`\]  
  
 *空白には*、空白またはタブで無視される構成される可能性がある; *符号は* \(**\+**\) または描画できます**–** \(\) ; `digits` とは、一つ以上の 10 進数です。  小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。  10 進数の後には指数部の開始文字 \(**d**、**D**、**e**、または **E**\) と符号付き整数からオプションで構成される指数を配置できます。  指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。  この形式に一致しない文字を見つけるとスキャンを停止します。  
  
 `strtol`、`strtoul`、`_strtoi64`と `_strtoui64` 関数は次のフォームの文字列を想定する:  
  
 *null*\[\] \[{**\+** &#124; **–**} \[\]**0** \[{ **x** &#124; **X** } \[\]\]`digits`\]  
  
 基本引数を 2 に、36 より大きい場合、数値のベースとして使用されます。  0 の場合ベースを決定するために、変換終了ポインターによって参照される最初の文字が使用されます。  最初の文字が 0、2 文字目が X または x でない場合は文字列の長さが 8;整数として解釈されます。それ以外の場合は 10 進数として解釈されます。  最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。  最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。  「z」の文字「a」 \(または「Z "、「A」\) 値 10 から 35;が割り当てられます。代入された値である *ベース* 未満文字だけです。  `strtoul` と `_strtoui64` \(**–**の\) をプレフィックスと**\+** \(\) または描画 a を使用して; 先頭の記号は、戻り値が拒否されることを示します。  
  
 出力値は、ロケールの `LC_NUMERIC` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  **\_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**\_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  
  
 これらの関数によって返される値がオーバーフローまたはアンダーフローが発生するか、変換が有効な場合、特殊な値は次のように戻ります:  
  
|関数|状態|返される値|  
|--------|--------|-----------|  
|`strtod`|オーバーフロー|\+\/\- `HUGE_VAL`|  
|`strtod`|アンダーフローまたは変換できません。|0|  
|`strtol`|\+ オーバーフロー|**LONG\_MAX**|  
|`strtol`|\-オーバーフロー|**LONG\_MIN**|  
|`strtol`|アンダーフローまたは変換できません。|0|  
|`_strtoi64`|\+ オーバーフロー|**\_I64\_MAX**|  
|`_strtoi64`|\-オーバーフロー|**\_I64\_MIN**|  
|`_strtoi64`|変換できません。|0|  
|`_strtoui64`|オーバーフロー|**\_UI64\_MAX**|  
|`_strtoui64`|変換できません。|0|  
  
 **\_I64\_MAX**、\_**I64\_MIN**、 **\_UI64\_MAX** は LIMITS.H.で定義されます。  
  
 `wcstod`、`wcstol`、`wcstoul`、`_wcstoi64`と `_wcstoui64` は `strtod`、`strtol`、`strtoul`、`_strtoi64`と `_strtoui64`のワイド文字バージョンであり、それぞれ;です これらのワイド文字単位の各関数への変換終了引数へのポインターはワイド文字列です。  それ以外の場合は、次のワイド文字単位の各関数は single\-byte–character の対応と同様に動作します。  
  
## 参照  
 [データ変換](../c-runtime-library/data-conversion.md)   
 [ロケール](../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [浮動小数点サポート](../c-runtime-library/floating-point-support.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)