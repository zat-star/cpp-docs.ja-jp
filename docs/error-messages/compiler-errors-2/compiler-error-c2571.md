---
title: "コンパイラ エラー C2571 | Microsoft Docs"
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
  - "C2571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2571"
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 仮想関数を共用体 'union' 内に含めることはできません。  
  
 共用体が仮想関数を持つように宣言されています。  仮想関数を宣言できるのは、クラスまたは構造体だけです。解決方法は次のとおりです。  
  
1.  共用体をクラスまたは構造体に変更します。  
  
2.  関数を非仮想関数に変更します。  
  
 次の例では警告 C2571 が生成されます。  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```