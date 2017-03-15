---
title: "ロケールのカテゴリ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LC_MAX"
  - "LC_MIN"
  - "LC_MONETARY"
  - "LC_TIME"
  - "LC_NUMERIC"
  - "LC_COLLATE"
  - "LC_CTYPE"
  - "LC_ALL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LC_ALL 定数"
  - "LC_COLLATE 定数"
  - "LC_CTYPE 定数"
  - "LC_MAX 定数"
  - "LC_MIN 定数"
  - "LC_MONETARY 定数"
  - "LC_NUMERIC 定数"
  - "LC_TIME 定数"
  - "ロケール定数"
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ロケールのカテゴリ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <locale.h>  
  
```  
  
## 解説  
 ロケールのカテゴリは、ローカライズ ルーチンが使用する記号定数であり、プログラムのロケール情報のどの部分を使用するかを指定します。  ロケールとは、地域性、つまり国または地域に関する情報であり、この情報に基づいてプログラムのさまざまな側面をカスタマイズできます。  ロケールに依存する部分としては、日付の形式や通貨の値の表示形式などがあります。  
  
|ロケール カテゴリ|影響を受けるプログラムの部分|  
|---------------|--------------------|  
|`LC_ALL`|ロケール固有のすべての動作 \(すべてのカテゴリ\)|  
|`LC_COLLATE`|`strcoll` 関数と `strxfrm` 関数の動作|  
|`LC_CTYPE`|文字処理関数の動作 \(ロケールとは関係のない **isdigit**、`isxdigit`、`mbstowcs`、および `mbtowc` を除く\)|  
|`LC_MAX`|`LC_TIME` と同じ|  
|`LC_MIN`|`LC_ALL` と同じ|  
|`LC_MONETARY`|`localeconv` 関数が返す通貨形式情報|  
|`LC_NUMERIC`|`printf` などの書式化出力ルーチン、データ変換ルーチン、および `localeconv` 関数が返す通貨形式以外の形式情報で使用される小数点文字|  
|`LC_TIME`|`strftime` 関数の動作|  
  
 例については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  
  
## 参照  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcoll 系関数](../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、\_strftime\_l、\_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、\_strxfrm\_l、\_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)