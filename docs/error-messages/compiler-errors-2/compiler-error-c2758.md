---
title: "コンパイラ エラー C2758 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2758"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2758"
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2758
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 参照型のメンバーは初期化する必要があります  
  
 初期化子リスト内の参照型のメンバーがコンストラクターによって初期化されていない場合、コンパイラ エラー C2758 が発生します。  コンパイラはそのメンバーを未定義のままにします。  参照型のメンバー変数は、コンストラクターの初期化リストで宣言されるか値を指定されるときに初期化する必要があります。  
  
 次の例では C2758 エラーが生成されます。  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```