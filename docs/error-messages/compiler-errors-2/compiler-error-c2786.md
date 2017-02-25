---
title: "コンパイラ エラー C2786 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2786"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2786"
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2786
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : \_\_uuidof の無効なオペランドです。  
  
 [\_\_uuidof](../../cpp/uuidof-operator.md) 演算子は、GUID がアタッチされたユーザー定義型またはそのようなユーザー定義型のオブジェクトを、引数として受け取ることができます。以下の原因が考えられます。  
  
1.  引数がユーザー定義型ではありません。  
  
2.  `__uuidof` が引数から GUID を取り出すことができません。  
  
 次の例では警告 C2786 が生成されます。  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```