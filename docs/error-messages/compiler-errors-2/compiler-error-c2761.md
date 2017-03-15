---
title: "コンパイラ エラー C2761 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2761"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2761"
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2761
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : メンバー関数の再宣言はできません。  
  
 メンバー関数は再宣言できません。  定義はできますが、再宣言はできません。  
  
## 使用例  
 次の例では C2761 エラーが生成されます。  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## 使用例  
 クラスまたは構造体の非静的メンバーは定義できません。次の例では C2761 エラーが生成されます。  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```