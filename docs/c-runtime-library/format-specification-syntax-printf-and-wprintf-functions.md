---
title: "書式指定構文: printf 関数と wprintf 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, precision
- type fields, printf function
- precision fields
- printf function, format specification fields
- flag directives printf function
- type fields
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
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
ms.openlocfilehash: 1843e4f826606f85aa96d1faf65e4af3f80769ea
ms.lasthandoff: 02/24/2017

---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>書式指定構文: printf 関数と wprintf 関数
`printf`、`wprintf`、および関連する関数への書式文字列の引数の構文について説明します。 これらの関数のセキュリティを強化したバージョンを使用できます。詳細については、「[CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)」を参照してください。 個々の関数の詳細については、特定の関数のドキュメントを参照してください。 これらの関数の一覧については、「[ストリーム入出力](../c-runtime-library/stream-i-o.md)」を参照してください。  
  
 省略可能なフィールドと必須フィールドで構成される書式指定には、次の形式があります。  
  
 `%`[[flags](../c-runtime-library/flag-directives.md)] [[width](../c-runtime-library/printf-width-specification.md)] [**.**[precision](../c-runtime-library/precision-specification.md)] [{`h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`}] [type](../c-runtime-library/printf-type-field-characters.md)  
  
 書式指定の各フィールドは、特定の書式オプションまたは変換指定子を示す数値です。 必須の `type` の文字では、引数に適用する変換の種類を指定します。 省略可能な `flags`、`width`、および `precision` のフィールドは、追加の書式の側面を制御します。 基本的な書式指定には、文字列変換を指定するパーセント記号と `type` の文字 (`%s` など) が含まれています。 セキュリティを強化したバージョンの関数では、パーセント記号の後に書式指定フィールドとして意味を持たない文字が続く場合、無効なパラメーター ハンドラーが呼び出されます。 詳細については、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」を参照してください。 セキュリティが万全ではないバージョンでは、文字は変更されずに出力にコピーされます。 パーセント記号の文字を出力するには、`%%` を使用します。  
  
 書式指定のフィールドは、引数の変換および書式設定の次の側面を制御します。  
  
 `type`  
 関連付けられた `argument` が文字、文字列、整数、または浮動小数点数として解釈されるかどうかを決定する、必須の変換指定子の文字。 詳細については、「[printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)」を参照してください。  
  
 `flags`  
 出力の行揃え、記号の出力、空白、先頭のゼロ、小数点、8 進数プレフィックス、および&16; 進数プレフィックスを制御する省略可能な文字 (複数可)。 詳細については、「[フラグ ディレクティブ](../c-runtime-library/flag-directives.md)」を参照してください。 書式指定では複数のフラグを表示でき、フラグは任意の順序で表示できます。  
  
 `width`  
 出力される最小文字数を指定する、省略可能な&10; 進数。 詳細については、「[printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)」を参照してください。  
  
 `precision`  
 文字列において出力される最大文字数、浮動小数点値における小数点文字以降の有効桁数または桁数、または整数値において出力される最小桁数を指定する、省略可能な&10; 進数。 詳細については、「[精度指定](../c-runtime-library/precision-specification.md)」の「有効桁数の値による型への影響」を参照してください。  
  
 `h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`  
 対応する引数のサイズを指定する `type` への省略可能なプレフィックス。 詳細については、「[サイズ指定](../c-runtime-library/size-specification.md)」の「サイズ プレフィックス」を参照してください。  
  
> [!IMPORTANT]
>  書式指定の文字列がユーザー定義ではないことを確認してください。 たとえば、名前の入力をユーザーに要求し、その入力を `name` という名前の文字列変数に格納するプログラムについて検討します。 `name` を出力するには、このように実行しないでください。  
>   
>  `printf( name ); /* Danger!  If name contains "%s", program will crash */`  
>   
>  代わりに、このように実行します。  
>   
>  `printf( "%s", name );`  
  
## <a name="see-also"></a>関連項目  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf_p の位置指定パラメーター](../c-runtime-library/printf-p-positional-parameters.md)   
 [フラグ ディレクティブ](../c-runtime-library/flag-directives.md)   
 [printf 関数の文字幅指定](../c-runtime-library/printf-width-specification.md)   
 [精度指定](../c-runtime-library/precision-specification.md)   
 [サイズ指定](../c-runtime-library/size-specification.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)
