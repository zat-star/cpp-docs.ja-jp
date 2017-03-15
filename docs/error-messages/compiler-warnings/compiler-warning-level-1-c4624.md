---
title: "コンパイラの警告 (レベル 1) C4624 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4624"
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'derived class' : 基底クラスのデストラクターへのアクセスまたはその削除ができないため、デストラクターを暗黙的に削除済みとして定義しました  
  
 デストラクターは基底クラスでアクセスできないか削除されているため、派生クラスでは生成されません。  スタックにこの型のオブジェクトを作成しようとすると、コンパイル エラーが発生します。  
  
 次の例では、C4624 を生成し、その修正方法を示しています。  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```