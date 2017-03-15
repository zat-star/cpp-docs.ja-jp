---
title: "コンパイラ エラー C2500 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2500"
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2500
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier1' : 'identifier2' クラスが、派生クラス用の基本クラスのリストに 2 か所以上あります。  
  
 クラスまたは構造体が、基本クラスのリストに 2 回以上出現しています。  
  
 基本クラスのリストに挙げられているクラスは、直接基本クラスと呼ばれます。  また、基本クラスのリストに挙げられているクラスの中のいずれかの基本クラスは、間接基本クラスと呼ばれます。  
  
 同じクラスを 2 回以上直接基本クラスに指定することはできません。  1 つのクラスを間接基本クラスとして 2 回以上使うことは可能です。  
  
 次の例では警告 C2500 が生成されます。  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```