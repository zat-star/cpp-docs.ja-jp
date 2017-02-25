---
title: "コンパイラ エラー C2892 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2892"
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ローカル クラスでメンバー テンプレートを使用することはできません。  
  
 template 宣言されたメンバー関数は、関数に定義されているクラスでは無効です。  
  
 次の例では警告 C2892 が生成されます。  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```