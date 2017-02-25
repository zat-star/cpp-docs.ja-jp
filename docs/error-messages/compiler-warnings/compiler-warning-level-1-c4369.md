---
title: "コンパイラの警告 (レベル 1) C4369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4369"
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'列挙子' :  列挙値 '値' は '型' として表示できません。値は 'new\_value' です。  
  
 列挙子を計算すると、指定された基になる型の最大値よりも大きくなりました。これによってオーバーフローが発生したので、コンパイラが列挙子の値をその型で可能な最小値にラップしました。  
  
## 使用例  
 次の例では C4369 エラーが生成されます。  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```