---
title: "コンパイラ エラー C2781 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2781"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2781"
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2781
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' : 最低でも value1 引数が必要です \- value2 が設定されます。  
  
 可変の数のパラメーター リストを持つ関数テンプレートの引数が少なすぎます。  
  
 次の例では警告 C2781 が生成されます。  
  
```  
// C2781.cpp  
template<typename T>  
void f(T, T, ...){}  
  
int main() {  
   f(1);   // C2781  
  
   // try the following line instead  
   f(1,1);  
}  
```