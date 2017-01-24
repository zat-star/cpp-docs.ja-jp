---
title: "コンパイラ エラー C2947 | Microsoft Docs"
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
  - "C2947"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2947"
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2947
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

construct を '\>' 終了という構文を使用します。  
  
 ジェネリック引数リストまたはテンプレート引数リストが、正しく終了されなかった可能性があります。  
  
 C2947 は、構文エラーでも生成されることがあります。  
  
 次の例では警告 C2947 が生成されます。  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```