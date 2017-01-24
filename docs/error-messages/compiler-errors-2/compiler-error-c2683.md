---
title: "コンパイラ エラー C2683 | Microsoft Docs"
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
  - "C2683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2683"
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'キャスト' : '型' はポリモーフィックな型ではありません。  
  
 [dynamic\_cast](../../cpp/dynamic-cast-operator.md) では、非ポリモーフィックなクラス、つまり仮想関数が定義されていないクラスからの変換はできません。  
  
 [static\_cast](../../cpp/static-cast-operator.md) を使用すると、非ポリモーフィックな型を変換できます。  ただし、`static_cast` ではランタイム チェックは実行されません。  
  
 次の例では警告 C2683 が生成されます。  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```