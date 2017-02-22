---
title: "コンパイラ エラー C2274 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2274"
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : '.' 演算子の右側で使用できません。  
  
 メンバー アクセス \(.\) 演算子の右側のオペランドとして型が使用されています。  
  
 このエラーは、ユーザー定義型の変換にアクセスしようとしたことが原因で発生する場合があります。  ピリオド \(.\) と `type` の間で `operator` キーワードを使用してください。  
  
 次の例では警告 C2286 が生成されます。  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```