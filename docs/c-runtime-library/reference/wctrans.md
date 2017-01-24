---
title: "wctrans | Microsoft Docs"
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
  - "wctrans"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wctrans"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "文字コード, wctrans"
  - "文字, コード"
  - "文字, 変換"
  - "wctrans 関数"
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1 組の文字コードから別のワークスペースにマッピングが決まります。  
  
## 構文  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### パラメーター  
 `property`  
 有効な変換の 1 を指定する文字列。  
  
## 戻り値  
 現在のロケールの `LC_CTYPE` のカテゴリがプロパティの名前を文字列 `property`に一致するマップを定義する、関数の戻り値を返します。  それ以外の場合は、後続の呼び出しに [towctrans](../../c-runtime-library/reference/towctrans.md)に使用に適した、2 番目の引数として 0 以外の値を返します。  
  
## 解説  
 この関数は、1 セットの文字コードから別のワークスペースにマッピングが決まります。  
  
 呼び出しの次のペアにすべてのロケールでも同じように動作しますが、引き続き「C」ロケールで追加のマッピングを定義することも可能です:  
  
|関数|同じと|  
|--------|---------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## 必要条件  
  
|ルーチン|必須のヘッダー|  
|----------|-------------|  
|`wctrans`|\<wctype.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
  **97**  
**1**  
**0**  
**65**   
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)