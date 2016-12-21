---
title: "コンパイラ エラー C3698 | Microsoft Docs"
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
  - "C3698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3698"
ms.assetid: 3c02fb08-7ba4-4637-a06f-19926cb2b5f1
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : この型を '演算子' の引数として使用できません  
  
 マネージ オブジェクトの宣言が正しくありません。  
  
 次の例では警告 C3698 が生成されます。  
  
```  
// C3698.cpp  
// compile with: /clr  
  
int main() {  
   array<int>^a = new array<int>^(20);   // C3698  
   array<int>^a2 = gcnew array<int>(20);   // OK  
}  
```