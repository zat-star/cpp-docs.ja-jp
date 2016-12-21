---
title: "コンパイラ エラー C3114 | Microsoft Docs"
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
  - "C3114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3114"
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'引数': 有効な名前付き属性引数ではありません  
  
 属性クラスのデータ メンバーを有効な名前付き引数にするには、それを `static`、`const`、または `literal` でマークしないでください。  プロパティの場合は、`static` にしないでください。また、get アクセサーおよび set アクセサーが必要です。  
  
 詳細については、「[property](../../windows/property-cpp-component-extensions.md)」および「[User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3114 エラーが生成されます。  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```