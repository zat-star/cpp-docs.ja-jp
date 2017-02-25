---
title: "コンパイラの警告 (レベル 3) C4534 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c4534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4534"
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 3) C4534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定の引数のため、'constructor' は class 'class' の既定のコンストラクターに指定できません。  
  
 アンマネージ クラスのコンストラクターは、既定値があるパラメーターを持つことができ、コンパイラはこのコンストラクターを既定のコンストラクターとして使用します。  `value` キーワードでマークされたクラスでは、パラメーターに既定値があるコンストラクターは、既定のコンストラクターとして使用されません。  
  
 詳細については、「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C4534 が生成されます。  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```