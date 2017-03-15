---
title: "rename_namespace | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rename_namespace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rename_namespace 属性"
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# rename_namespace
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 タイプ ライブラリの内容を含む名前空間の名前を変更します。  
  
## 構文  
  
```  
rename_namespace("NewName")  
```  
  
#### パラメーター  
 `NewName`  
 名前空間の新しい名前。  
  
## 解説  
 これは、名前空間の新しい名前を指定する単一の *NewName* 引数を受け取ります。  
  
 名前空間を削除するには、代わりに [no\_namespace](../Topic/no_namespace.md) 属性を使用します。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)