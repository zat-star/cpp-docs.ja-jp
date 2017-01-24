---
title: "コンパイラ エラー C3768 | Microsoft Docs"
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
  - "C3768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3768"
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

仮想 vararg 関数のアドレスを純粋マネージ コードで指定できません  
  
 `/clr:pure` でコンパイルする場合は、仮想 `vararg` 関数のアドレスを指定できません。  
  
 次の例では警告 C3768 が生成されます。  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```