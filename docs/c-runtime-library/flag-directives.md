---
title: "フラグ ディレクティブ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, format specification fields
- flag directives printf function
ms.assetid: b00cbdc9-1e5c-4b30-9f56-c1ef8d383767
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 36f7db99d3fc9bb5346ae5f1dc96b846ae964714
ms.lasthandoff: 02/24/2017

---
# <a name="flag-directives"></a>フラグ ディレクティブ
書式指定の最初の任意フィールドは `flags` です。 フラグ ディレクティブは、出力の行揃え、記号の出力、空白、先頭のゼロ、小数点、8 進数プレフィックス、16 進数プレフィックスを指定する文字です。 書式指定には、複数のフラグ ディレクティブが表示されることがあります。フラグは任意の順序で表示できます。  
  
### <a name="flag-characters"></a>フラグ文字  
  
|フラグ|説明|既定値|  
|----------|-------------|-------------|  
|`–`|指定されたフィールド幅内で結果を左揃えにします。|右揃えにします。|  
|`+`|符号付きの場合に出力値にプレフィックスを付けるには、記号 (+ または –) を使用します。|記号は、マイナス記号 (–) 付きの値にのみ表示されます。|  
|`0`|`width` に `0` というプレフィックスが付いている場合、最小幅に到達するまで先頭にゼロが追加されます。 `0` と `–` の両方が表示される場合、`0` は無視されます。 `0` が整数形式 (`i`、`u`、`x`、`X`、`o`、`d`) で指定されるとき、有効桁数も指定されている場合 (`%04.d` など)、`0` は無視されます。|パディングなし。|  
|空白 (' ')|記号付きでプラスの場合に出力値にプレフィックスを付けるには、空白を使用します。 空白と + フラグの両方が表示される場合、空白は無視されます。|空白は表示されません。|  
|`#`|`o`、`x`、`X` 形式で使用されるとき、`#` フラグはそれぞれ 0、0x、0X を使用し、ゼロ以外の出力値にプレフィックスを付けます。|空白は表示されません。|  
||`e`、`E`、`f`、`a`、`A` 形式が使用されるとき、`#` フラグは小数点を追加するように出力値に強制します。|小数点は、数字が続く場合にのみ表示されます。|  
||`g` または `G` 形式が使用されるとき、`#` フラグは小数点を追加するように出力値に強制し、後続のゼロの切り詰めを防止します。<br /><br /> `c`、`d`、`i`、`u`、`s` と共に使用されるときは無視されます。|小数点は、数字が続く場合にのみ表示されます。 後続のゼロは切り詰められます。|  
  
## <a name="see-also"></a>関連項目  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [書式指定構文: printf 関数と wprintf 関数](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [精度指定](../c-runtime-library/precision-specification.md)   
 [サイズ指定](../c-runtime-library/size-specification.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)
