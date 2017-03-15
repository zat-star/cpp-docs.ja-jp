---
title: "towctrans | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "towctrans"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "towctrans"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "towctrans 関数"
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# towctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字を変換します。  
  
## 構文  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### パラメーター  
 `c`  
 変更する文字。  
  
 `category`  
 [wctrans](../../c-runtime-library/reference/wctrans.md)の戻り値を含む ID。  
  
## 戻り値  
 `towctrans` の後の文字 `c`は、`category`で変換規則を使用します。  
  
## 解説  
 `category` の値は [wctrans](../../c-runtime-library/reference/wctrans.md)により早く正常な呼び出しによって返されることになります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`towctrans`|\<wctype.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 `towctrans`を使用するサンプルの `wctrans` を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)