---
title: "コンパイラ エラー C3625 | Microsoft Docs"
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
  - "C3625"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3625"
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3625
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'native\_type': ネイティブ型はマネージ型または WinRT 型の 'type' から派生することはできません  
  
 マネージ クラスまたは WinRT クラスからネイティブ クラスを継承できません。  詳細については、「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3625 が生成されます。  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
  
 次の例では警告 C3625 が生成されます。  
  
```  
// C3625_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class B {};  
class D : public B {};   // C3625  cannot inherit from a managed class  
```