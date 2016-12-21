---
title: "コンパイラ エラー C3153 | Microsoft Docs"
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
  - "C3153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3153"
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : インターフェイスのインスタンスを作成することはできません。  
  
 インターフェイスはインスタンス化できません。  インターフェイスのメンバーを使用するには、インターフェイスからクラスを派生し、インターフェイスのメンバーを実装してからメンバーを使用します。  
  
 次の例では警告 C3153 が生成されます。  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
  
 次の例では警告 C3153 が生成されます。  
  
```  
// C3153b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__interface A {  
};  
  
int main() {  
   A *a = new A;   // C3153  
}  
```