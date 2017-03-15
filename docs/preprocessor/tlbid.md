---
title: "tlbid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tlbid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlbid 属性"
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# tlbid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。  
  
## 構文  
  
```  
tlbid(number)  
```  
  
#### パラメーター  
 `number`  
 `filename` のタイプ ライブラリの番号。  
  
## 解説  
 複数のタイプ ライブラリが 1 つの DLL に組み込まれている場合、`tlbid` を使用してプライマリ タイプ ライブラリ以外のライブラリを読み込むことができます。  
  
 次に例を示します。  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 上の式は、下の式と同等です。  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)