---
title: "コンパイラ エラー C2180 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2180"
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C2180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

制御式には、型 'type' が指定されています。  
  
 `if`、`while`、`for`、`do` のいずれかのステートメントの制御式は、`void` にキャストした式です。  この問題を解決するには、制御式を、`bool` を生成する制御式または `bool` に変換できる型に変更します。  
  
 次の例では C2180 が生成されます。  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```