---
title: "Compiler Error C3387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3387"
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compiler Error C3387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : \_\_declspec\(dllexport\)\/\_\_declspec\(dllimport\) はマネージ型または WinRT 型のメンバーに適用できません  
  
 `dllimport` および [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` 修飾子は、マネージ型または Windows ランタイム型のメンバーでは有効でありません。  
  
 次の例では C3387 を生成し、その修正方法を示しています。  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```