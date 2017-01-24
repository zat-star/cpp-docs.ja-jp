---
title: "EOF、WEOF | Microsoft Docs"
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
  - "EOF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "EOF 関数"
  - "WEOF 関数"
  - "EOF (ファイル終端)"
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EOF、WEOF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <stdio.h>  
```  
  
## 解説  
 EOF が I\/O ルーチンによって EOF \(や場合によっては、エラーの発生時に返されます。  
  
 WEOF は、広範なストリームの末尾に通知やエラーを報告するために使用される戻り値を、型 **wint\_t**の導入されています。  
  
## 参照  
 [putc、putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc、ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../Topic/fflush.md)   
 [fclose、\_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_ungetch、\_ungetwch、\_ungetch\_nolock、\_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [\_putch、\_putwch](../Topic/_putch,%20_putwch.md)   
 [isascii、\_ \_isascii、iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)