---
title: "コンパイラの警告 (レベル 4) C4516 | Microsoft Docs"
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
  - "C4516"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4516"
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4516
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::symbol' : access 宣言の使用は避けてください; メンバー using 宣言を使用してください。  
  
 ANSI C\+\+ 委員会では、アクセス宣言 \([using](../../cpp/using-declaration.md) キーワードを使用せずに、派生クラスのメンバーのアクセスを変えること\) は旧式であるとしています。  将来のバージョンの C\+\+ では、アクセス宣言がサポートされない可能性があります。  
  
 次の例では警告 C4516 が生成されます。  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```