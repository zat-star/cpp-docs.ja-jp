---
title: "___setlc_active_func、___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___unguarded_readlc_active_add_func"
  - "___setlc_active_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ___setlc_active_func、___unguarded_readlc_active_add_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

互換性のために残されています。  バイナリの互換性を維持するためにのみ、これらの内部関数は CRT によってエクスポートされます。  
  
## 構文  
  
```cpp  
int ___setlc_active_func(void); int * ___unguarded_readlc_active_add_func(void);  
```  
  
## 戻り値  
 戻される値は重要ではありません。  
  
## 解説  
 内部 CRT 関数 `___setlc_active_func` および `___unguarded_readlc_active_add_func` は互換性のために残されており、使用されなくなりましたが、バイナリの互換性を維持するために CRT ライブラリによってエクスポートされます。  `___setlc_active_func` の本来の目的は、`setlocale` 関数の現在アクティブな呼び出しの数を返すことでした。  `___unguarded_readlc_active_add_func` の本来の目的は、ロケールをロックしないで参照した関数の数を返すことでした。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|none|  
  
## 参照  
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)