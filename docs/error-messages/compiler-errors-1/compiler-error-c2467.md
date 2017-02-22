---
title: "コンパイラ エラー C2467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2467"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2467"
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2467
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無名の 'user\-defined\-type' の宣言が誤っています。  
  
 入れ子になったユーザー定義型が宣言されています。  このエラーは、ANSI 互換のオプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md) オプション\) を指定して C ソース コードをコンパイルしたときだけに発生します。  
  
 次の例では警告 C2467 が生成されます。  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```