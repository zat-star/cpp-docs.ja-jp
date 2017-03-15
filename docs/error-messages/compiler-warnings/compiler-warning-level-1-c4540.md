---
title: "コンパイラの警告 (レベル 1) C4540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4540"
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

dynamic\_cast がアクセスできない、またはあいまいなベースへの変換に使用されています; 'type1' から 'type2' の変換でランタイム テストが失敗します。  
  
 `dynamic_cast` を使用して、ある型から別の型への変換を行っています。  コンパイラは、基本クラスがアクセス不能 \(`private` など\) であるか、あいまい \(クラス階層に 2 回以上表示されるなど\) であるため、キャストが常に失敗する \(**NULL** を返す\) と判断しました。  
  
 以下にこの警告の例を示します。  クラス **B** はクラス **A** から派生します。  プログラムは `dynamic_cast` を使用して、クラス **B** \(派生クラス\) からクラス **A** へのキャストを行いますが、クラス **B** は `private` でアクセス不能なため、この操作は常に失敗します。  **A** のアクセスを **public** に変えると、この警告は解決します。  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```