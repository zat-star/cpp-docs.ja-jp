---
title: "___lc_codepage_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___lc_codepage_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lc_codepage_func"
  - "___lc_codepage_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_codepage_func"
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# ___lc_codepage_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

内部 CRT 関数。  スレッドの現在のコード ページを取得します。  
  
## 構文  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## 戻り値  
 スレッドの現在のコード ページ。  
  
## 解説  
 `___lc_codepage_func` は、CRT データのスレッド ローカル ストレージから現在のコード ページを取得するために、他の CRT 関数によって使用される内部 CRT 関数です。  この情報は、[\_get\_current\_locale](../Topic/_get_current_locale.md) 関数を使用して取得することもできます。  
  
 *コード ページ*は、個別の文字への 1 バイト コードまたは 2 バイト コードのマッピングです。  異なるコード ページには異なる特殊文字が含まれ、それらは通常は 1 つの言語または言語グループ用にカスタマイズされています。  コード ページの詳細については、「[コード ページ](../c-runtime-library/code-pages.md)」を参照してください。  
  
 内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。  コード内では使用しないことをお勧めします。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`___lc_codepage_func`|crt\\src\\setlocal.h|  
  
## 参照  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale、\_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)