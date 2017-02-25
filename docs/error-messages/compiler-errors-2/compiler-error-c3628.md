---
title: "コンパイラ エラー C3628 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3628"
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'base class' : マネージ クラスまたは WinRT クラスはパブリック継承のみをサポートしています  
  
 マネージ クラスまたは WinRT クラスを [private](../Topic/private%20\(C++\).md) または [protected](../Topic/protected%20\(C++\).md) 基底クラスとして使用しようとしました。  マネージ クラスまたは WinRT クラスは、[パブリック](../../cpp/public-cpp.md) アクセスを持つ基底クラスとしてのみ使用できます。  
  
 次の例は C3628 を生成し、その修正方法を示しています。  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
  
 次の例は C3628 を生成し、その修正方法を示しています。  
  
```  
// C3628b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class B {  
};  
  
__gc class D : B {   // C3628, private is the default access level  
  
// The following line resolves the error.  
// __gc class D : public B {  
};  
  
int main() {  
}  
```