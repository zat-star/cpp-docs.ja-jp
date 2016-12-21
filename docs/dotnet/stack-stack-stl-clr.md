---
title: "stack::stack (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stack メンバー [STL/CLR]"
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーのアダプター オブジェクトを構築します。  
  
## 構文  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### パラメーター  
 \[right\]  
 コピーするオブジェクト。  
  
 ラップされる  
 使用するラップされたコンテナー。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `stack();`  
  
 空のラップされたコンテナーを作成します。  空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `stack(stack<Value, Container>% right);`  
  
 `right.get_container()`のコピーであるラップされたコンテナーを作成します。  スタック `right`オブジェクトによって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `stack(stack<Value, Container>^ right);`  
  
 `right->get_container()`のコピーであるラップされたコンテナーを作成します。  スタック `*right`オブジェクトによって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `explicit stack(container_type% wrapped);`  
  
 ラップされたコンテナーとして既存のコンテナー `wrapped` を使用します。  既存のコンテナーからスタックを構築するときに使用します。  
  
## 使用例  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **X x x x X**  
 **X x x x X**  
 **X x x x X**   
## 必要条件  
 **ヘッダー:** \<cliext とスタック\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [スタック](../dotnet/stack-stl-clr.md)   
 [stack::assign](../Topic/stack::assign%20\(STL-CLR\).md)   
 [stack::generic\_container](../Topic/stack::generic_container%20\(STL-CLR\).md)   
 [stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)