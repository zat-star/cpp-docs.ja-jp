---
title: "raw_property_prefixes | Microsoft Docs"
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
  - "raw_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_property_prefixes 属性"
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## 構文  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### パラメーター  
 `GetPrefix`  
 **propget** メソッドに使用されるプレフィックス。  
  
 `PutPrefix`  
 **propput** メソッドに使用されるプレフィックス。  
  
 `PutRefPrefix`  
 **propputref** メソッドに使用されるプレフィックス。  
  
## 解説  
 既定では、低レベルの **propget**、**propput**、および **propputref** メソッドは、それぞれ名前に **get\_**、**put\_**、および **putref\_** というプレフィックスを持つメンバー関数によって公開されます。  これらのプレフィックスは、MIDL によって生成されるヘッダー ファイルで使用される名前と互換性があります。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)