---
title: "コンパイラ エラー C2601 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2601"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2601"
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2601
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : ローカル関数の定義が正しくありません。  
  
 関数内で関数の定義を試みました。  
  
 または、ソース コード内の C2601 エラー位置の前に、余分な中かっこが含まれている可能性があります。  
  
 次の例では警告 C2601 が生成されます。  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```