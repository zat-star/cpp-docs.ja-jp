---
title: "コンパイラ エラー C2348 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2348"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2348"
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2348
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type name' : C 形式の集合ではありません、埋め込み IDL 内でエクスポートできません。  
  
 [export](../../windows/export.md) 属性を使用して `struct` を .idl ファイルに配置する場合、`struct` に入れることができるのはデータだけです。  
  
 次の例では警告 C2348 が生成されます。  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```