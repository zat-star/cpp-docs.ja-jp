---
title: "コンパイラ エラー C3766 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3766"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3766"
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラ エラー C3766
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' インターフェイス メソッド  '関数' の実装を提供しなければなりません  
  
 インターフェイスから継承するクラスは、インターフェイスのメンバーを実装する必要があります。  
  
## 使用例  
 次の例では C3766 エラーが生成されます。  
  
```  
// C3766.cpp  
// compile with: /clr /c  
  
delegate void MyDel();  
  
interface struct IFace {  
   virtual event MyDel ^ E;  
};  
  
ref struct Class1 : public IFace {};   // C3766  
  
// OK  
ref struct Class2 : public IFace {  
   virtual event MyDel ^ E {  
      void add(MyDel ^) {}  
      void remove(MyDel ^) {}  
   }  
};  
```