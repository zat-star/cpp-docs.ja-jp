---
title: "___lc_locale_name_func | Microsoft Docs"
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
  - "___lc_locale_name_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_locale_name_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_locale_name_func"
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_locale_name_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

内部 CRT 関数。  スレッドの現在のロケール名を取得します。  
  
## 構文  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## 戻り値  
 スレッドの現在のロケール名を含む文字列へのポインター。  
  
## 解説  
 `___lc_locale_name_func` は、CRT データのスレッド ローカル ストレージから現在のロケール名を取得するために、他の CRT 関数によって使用される内部 CRT 関数です。  この情報は、[\_get\_current\_locale](../Topic/_get_current_locale.md) 関数または [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md) 関数を使用して取得することもできます。  
  
 内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。  コード内では使用しないことをお勧めします。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`___lc_locale_name_func`|crt\\src\\setlocal.h|  
  
## 参照  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale、\_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)