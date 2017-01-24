---
title: "コンパイラ エラー C3113 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3113"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3113"
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3113
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'構造体' は 'template\/generic' にはできません。  
  
 インターフェイスまたは列挙型の外側でクラス テンプレートまたはクラス ジェネリックを使用しようとしました。  
  
 次の例では警告 C3113 が生成されます。  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```