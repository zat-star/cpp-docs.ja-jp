---
title: "コンパイラ エラー C2751 | Microsoft Docs"
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
  - "C2751"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2751"
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2751
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter' : 関数パラメーターの名前は修飾できません。  
  
 限定名は関数パラメーターとして使用できません。  
  
 次の例では警告 C2751 が生成されます。  
  
```  
// C2751.cpp  
namespace std {  
   template<typename T>  
   class list {};  
}  
  
#define list std::list  
void f(int &list){}   // C2751  
```