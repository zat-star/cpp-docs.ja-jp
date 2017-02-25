---
title: "wctype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctype"
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
  - "wctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wctype 関数"
  - "ワイド文字"
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# wctype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字コードの分類の規則を指定します。  
  
## 構文  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### パラメーター  
 `property`  
 プロパティの文字列。  
  
## 戻り値  
 現在のロケールの `LC_CTYPE` のカテゴリがプロパティの名前を文字列 `property`に合わせて調整規則を定義する、関数の戻り値を返します。  それ以外の場合は、後続の呼び出しに [towctrans](../../c-runtime-library/reference/towctrans.md)に使用に適した、2 番目の引数として 0 以外の値を返します。  
  
## 解説  
 関数が文字コードの分類の規則を指定します。  呼び出しの次のペアにすべてのロケールで同じ動作です \(実装が引き続き「C」ロケールの追加分類の規則を定義する:\)  
  
|関数|同じと|  
|--------|---------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`wctype`|\<wctype.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)