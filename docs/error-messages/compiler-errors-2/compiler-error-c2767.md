---
title: "コンパイラ エラー C2767 | Microsoft Docs"
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
  - "C2767"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2767"
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2767
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マネージ配列または WinRT 配列の次元の不一致です: N 個の引数が必要ですが M 個が指定されました  
  
 マネージ配列または WinRT 配列の宣言の形式が正しくありません。  詳細については、「[配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では、C2767 を生成し、その修正方法を示しています。  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```