---
title: "コンパイラ エラー C2427 | Microsoft Docs"
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
  - "C2427"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2427"
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2427
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : このスコープではクラスを定義できません  
  
 入れ子になったクラスを定義しようとしましたが、そのクラスは基本クラスのメンバーであり、最も外側のクラスではありません。  
  
 次の例では警告 C2427 が生成されます。  
  
```  
// C2427.cpp  
// compile with: /c  
template <class T>   
struct S {  
   struct Inner;   
};   
  
struct Y : S<int> {};   
  
struct Y::Inner {};   // C2427  
  
// OK  
template<typename T>  
struct S<T>::Inner {};  
```