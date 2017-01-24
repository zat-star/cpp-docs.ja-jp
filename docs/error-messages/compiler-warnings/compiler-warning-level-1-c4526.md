---
title: "コンパイラの警告 (レベル 1) C4526 | Microsoft Docs"
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
  - "C4526"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4526"
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4526
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : スタティック メンバー関数は仮想関数をオーバーライドできません 'virtual function' オーバーライドは無視されます、仮想関数は隠されます。  
  
 静的メンバー関数は、仮想関数をオーバーライドするための基準を満たしています。このメンバー関数は仮想関数であり静的関数です。  
  
 次のコードは C4526 を生成します。  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 考えられる修正方法は、次のとおりです。  
  
-   関数が基本クラスの仮想関数をオーバーライドするための関数である場合は、静的指定子を削除します。  
  
-   関数を静的なメンバー関数とする場合は、関数名を変更して基本クラスの仮想関数と競合しないようにします。