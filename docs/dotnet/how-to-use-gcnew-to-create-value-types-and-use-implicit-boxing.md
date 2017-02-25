---
title: "方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ボックス化, implicit"
  - "gcnew キーワード [C++], 作成 (値型を)"
  - "値型, 作成"
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値型の [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) を使用してマネージに配置できるボックス化された値型、ガベージ コレクション ヒープ作成します。  
  
## 使用例  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## 参照  
 [Boxing](../windows/boxing-cpp-component-extensions.md)