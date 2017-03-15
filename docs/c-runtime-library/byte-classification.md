---
title: "バイト分類 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types.bytes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "バイト分類ルーチン"
  - "バイト, テスト"
  - "コード ページ 932"
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# バイト分類
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのルーチンでは、条件のコンテンツにマルチバイト文字の指定されたバイトをテストします。  別の方法で指定されている場合、出力値は、ロケールの `LC_CTYPE` カテゴリの設定の影響を受ける以外; 詳細については、" [setlocale](../Topic/setlocale,%20_wsetlocale.md) を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  
  
> [!NOTE]
>  定義上、0 ~ 127 の ASCII 文字はすべてのマルチバイト文字セットのサブセットです。  たとえば、日本語のカタカナ文字セットは ASCII、ASCII 文字以外の文字が含まれています。  
  
 次の表に定義済みのな定数は CTYPE.H.で定義されます。  
  
### マルチバイト文字のバイト分類ルーチン  
  
|ルーチン|バイトのテスト条件|同等の .NET Framework 関数|  
|----------|---------------|---------------------------|  
|[isleadbyte、\_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|先行バイト; テスト結果は、現在のロケールの `LC_CTYPE` のカテゴリの設定によって異なります。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbalnum、\_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum &#124;&#124; _ismbbkalnum`|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbalpha、\_ismbbalpha\_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|`isalpha &#124;&#124; _ismbbkalnum`|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbgraph、\_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|`_ismbbprint`と同様ですが、`_ismbbgraph` は含まれません空白文字 \(0x20\) を|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbkalnum、\_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|区切り記号以外の非 ASCII テキストの記号。  たとえば、コード ページ 932 には、`_ismbbkalnum` は英数字カタカナをテストします。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbkana、\_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|カタカナ \(0xA1 – 0xDF\)、932 ページ コードのみ|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbkprint、\_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|非 ASCII テキストまたは ASCII 以外の区切り記号。  たとえば、コード ページ 932 でのみ、`_ismbbkprint` はカタカナの英数字、またはカタカナの句読点 \(範囲: 0xA1 ～ 0xDF\) をテストします。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbkpunct、\_ismbbkpunct\_l](../Topic/_ismbbkpunct,%20_ismbbkpunct_l.md)|ASCII 以外の区切り記号。  たとえば、コード ページ 932 でのみ `_ismbbkpunct` は、カタカナ区切り文字をテストします。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbblead、\_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|マルチバイト文字の最初のバイト。  たとえば、コード ページ 932 でのみ、有効な範囲は 0x81 – 0x9F、0xE0 – 0xFC です。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbprint、\_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint &#124;&#124; _ismbbkprint. ismbbprint` に含まれる空白文字 \(0x20\) を|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbpunct、\_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct &#124;&#124; _ismbbkpunct`|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbbtrail、\_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|マルチバイト文字の 2 番目のバイト。  たとえば、コード ページ 932 でのみ、有効な範囲は 0x40 – 0x7E、0x80 – 0xEC です。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_ismbslead、\_ismbslead\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|先行バイト \(文字列のコンテキスト内\)|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[ismbstrail、\_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|後続バイト \(文字列のコンテキスト内\)|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_mbbtype、\_mbbtype\_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|前のバイトに基づいて、byte 型|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[\_mbsbtype、\_mbsbtype\_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|文字列内のバイトの戻り値の型|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|マルチバイト文字の変換状態を追跡します。|適用、[System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)を参照してください。|  
  
 LIMITS.H で定義されている `MB_LEN_MAX` マクロは既存のマルチバイト文字ができる最大バイト長に展開します。  STDLIB.H に定義されている`MB_CUR_MAX`は現在のロケールのすべてのマルチバイト文字のバイトの最大長に展開します。  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)