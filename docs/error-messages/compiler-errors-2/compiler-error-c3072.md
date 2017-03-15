---
title: "コンパイラ エラー C3072 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3072"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3072"
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3072
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

演算子 '演算子' は ref クラスのインスタンスに適用できません。  
  
 ref クラスのインスタンスをハンドル型に変換するには、単項 '`operator` ' 演算子を使用してください。  
  
 CLR 型には、ネイティブ \(標準\) 演算子ではなく CLR 演算子が必要です。詳細については、「[Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3072 エラーが生成されます。  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```