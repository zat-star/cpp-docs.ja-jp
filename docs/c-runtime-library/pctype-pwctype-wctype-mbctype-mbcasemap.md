---
title: "_pctype、_pwctype、_wctype、_mbctype、_mbcasemap | Microsoft Docs"
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
  - "pwctype"
  - "pctype"
  - "mbctype"
  - "mbcasemap"
  - "_mbcasemap"
  - "_mbctype"
  - "_pctype"
  - "_wctype"
  - "_pcwtype"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wctype 関数"
  - "_pwctype 関数"
  - "_pctype 関数"
  - "_mbctype 関数"
  - "wctype 関数"
  - "pwctype 関数"
  - "pctype 関数"
  - "mbcasemap 関数"
  - "mbctype 関数"
  - "_mbcasemap 関数"
ms.assetid: 7f5e1107-c43b-4b9b-b387-781e6d2373cb
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _pctype、_pwctype、_wctype、_mbctype、_mbcasemap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのグローバル変数は文字分類関数で使用される情報を含みます。  これらは、内部でのみ使用します。  
  
## 構文  
  
```  
extern const unsigned short *_pctype;  
extern const wctype_t *_pwctype;  
extern const unsigned short _wctype[];  
extern unsigned char _mbctype[];  
extern unsigned char _mbcasemap[];  
```  
  
## 解説  
 `_pctype`の情報は、`_pwctype`と `_wctype` 関数 [isupper、\_isupper\_l、iswupper、\_iswupper\_l](../Topic/isupper,%20_isupper_l,%20iswupper,%20_iswupper_l.md)、[islower、iswlower、\_islower\_l、\_iswlower\_l](../Topic/islower,%20iswlower,%20_islower_l,%20_iswlower_l.md)、[isdigit、iswdigit、\_isdigit\_l、\_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)、[isxdigit、iswxdigit、\_isxdigit\_l、\_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)、[isspace、iswspace、\_isspace\_l、\_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)、[isalnum、iswalnum、\_isalnum\_l、\_iswalnum\_l](../Topic/isalnum,%20iswalnum,%20_isalnum_l,%20_iswalnum_l.md)、[ispunct、iswpunct、\_ispunct\_l、\_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)、[isgraph、iswgraph、\_isgraph\_l、\_iswgraph\_l](../Topic/isgraph,%20iswgraph,%20_isgraph_l,%20_iswgraph_l.md)と [iscntrl、iswcntrl、\_iscntrl\_l、\_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)、[toupper、\_toupper、towupper、\_toupper\_l、\_towupper\_l](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md) と [tolower、\_tolower、towlower、\_tolower\_l、\_towlower\_l](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md) 関数によって内部的に使用されます。  これらの関数は、これらのグローバル変数にアクセスする代わりに使用する必要があります。  
  
 `_mbctype` と `_mbcasemap` の情報は、[\_ismbbkalnum、\_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)[\_ismbbkana、\_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)、[\_ismbbkpunct、\_ismbbkpunct\_l](../Topic/_ismbbkpunct,%20_ismbbkpunct_l.md)、[\_ismbbkprint、\_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)、[\_ismbbalpha](http://msdn.microsoft.com/ja-jp/8e54cb92-fc2b-41f5-8ab4-b22ac8aa9ad0)、[\_ismbbpunct、\_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)、[\_ismbbalnum、\_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)、[\_ismbbprint、\_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)、[\_ismbbgraph、\_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)、[\_ismbblead、\_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)、[\_ismbbtrail、\_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)、[\_ismbslead、\_ismbstrail、\_ismbslead\_l、\_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)と [\_ismbslead、\_ismbstrail、\_ismbslead\_l、\_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)で内部的に使用されます。  グローバル変数にアクセスするのではなく、これらの関数を使用します。  
  
## 必要条件  
 ないパブリックな使用に。  
  
## 参照  
 [is、isw 系ルーチン](../c-runtime-library/is-isw-routines.md)   
 [\_\_pctype\_func](../c-runtime-library/pctype-func.md)