---
title: "コンパイラ エラー C3797 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3797"
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラ エラー C3797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'オーバーライド': イベント宣言は、オーバーライド指定子を含むことはできません。イベントの add、remove、または raise メソッドに配置しなければなりません  
  
 単純なイベント \(アクセサー メソッドが明示的に定義されていないイベント\) を別の単純なイベントでオーバーライドすることはできません。  オーバーライドするイベントは、アクセサー関数でその動作を定義する必要があります。  
  
 詳細については、「[event](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3797 エラーが生成されます。  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```