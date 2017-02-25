---
title: "コンパイラ エラー C2351 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2351"
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

互換性のために残されている C\+\+ コンストラクター初期化構文です。  
  
 コンストラクターの新しいスタイルの初期化リストでは、基本クラスが 1 つしかないとしても、直接基本クラスの名前を明示的に指定する必要があります。  
  
 次の例では警告 C2351 が生成されます。  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```