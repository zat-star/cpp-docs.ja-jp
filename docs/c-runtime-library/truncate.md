---
title: "_TRUNCATE | Microsoft Docs"
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
  - "_TRUNCATE"
  - "TRUNCATE"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_TRUNCATE 定数"
  - "TRUNCATE 定数"
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _TRUNCATE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字列の切り捨て動作を指定します。  
  
## 構文  
  
```  
#include <stdlib.h>  
```  
  
## 解説  
 `_TRUNCATE` は これらの関数に `count` パラメーターとして渡された場合、切り捨て動作を有効にする:  
  
 [strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)  
  
 [strncat\_s、\_strncat\_s\_l、wcsncat\_s、\_wcsncat\_s\_l、\_mbsncat\_s、\_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [mbstowcs\_s、\_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 [mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)  
  
 [wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)  
  
 [wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)  
  
 [\_snprintf\_s、\_snprintf\_s\_l、\_snwprintf\_s、\_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s、\_vsnprintf\_s、\_vsnprintf\_s\_l、\_vsnwprintf\_s、\_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
 コピー先のバッファーのワイド文字列を保持するには小さすぎて関数の通常の動作は、エラー状態であることを扱うことです \([パラメーターの検証](../c-runtime-library/parameter-validation.md)を参照してください。  ただし、文字列の切り捨てが `_TRUNCATE`を渡すことにより、有効になっている場合、これらの関数には、正常に返します。収まるように文字列までしかコピーし、変換先バッファーを null で終わる。  
  
 切り捨て変更の影響を受ける関数の戻り値文字列です。  次の関数は、切り捨てがある切り捨てが実行されていない場合、または `STRUNCATE` : 0 を返します。  
  
 [strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)  
  
 [strncat\_s、\_strncat\_s\_l、wcsncat\_s、\_wcsncat\_s\_l、\_mbsncat\_s、\_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [wcstombs\_s、\_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)  
  
 [mbstowcs\_s、\_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 次の関数は、切り捨てがある切り捨てが実行されていない場合、または \-1 を返し、コピーする文字数 \(snprintf の元の関数の実行に一致\) :  
  
 [\_snprintf\_s、\_snprintf\_s\_l、\_snwprintf\_s、\_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf\_s、\_vsnprintf\_s、\_vsnprintf\_s\_l、\_vsnwprintf\_s、\_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
## 使用例  
  
```  
// crt_truncate.c  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
   char src[] = "1234567890";  
   char dst[5];  
   errno_t err = strncpy_s(dst, _countof(dst), src, _TRUNCATE);  
   if ( err == STRUNCATE )  
      printf( "truncation occurred!\n" );  
   printf( "'%s'\n", dst );  
}  
```  
  
  **切り捨てが発生しました。**  
**'1234'**   
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)