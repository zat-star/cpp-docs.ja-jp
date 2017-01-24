---
title: "コンパイラの警告 (レベル 1) C4488 | Microsoft Docs"
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
  - "C4488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4488"
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : インターフェイス メソッド 'interface\_method' を実装するには 'キーワード' キーワードが必要です  
  
 クラスは、直接継承するインターフェイスのすべてのメンバーを実装する必要があります。  実装されるメンバーにはパブリック アクセシビリティが必要で、仮想として設定されることも必要です。  
  
## 使用例  
 C4488 は、実装されるメンバーがパブリックでない場合に発生します。  次の例では C4488 エラーが生成されます。  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## 使用例  
 C4488 は、実装されるメンバーが仮想として設定されていない場合に発生します。  次の例では C4488 エラーが生成されます。  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```