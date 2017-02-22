---
title: "コンパイラの警告 (レベル 4) C4208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4208"
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : delete \[exp\] \- exp を評価しましたが無視します。  
  
 Microsoft 拡張機能 \(\/Ze\) では、角かっこ \(\[\]\) で囲んだ値を [delete 演算子](../../cpp/delete-operator-cpp.md)で使用して配列を削除できます。  値は無視されます。  
  
```  
// C4208.cpp  
// compile with: /W4  
int main()  
{  
   int * MyArray = new int[18];  
   delete [18] MyArray;      // C4208  
   MyArray = new int[18];  
   delete [] MyArray;        // ok  
}  
```  
  
 このような値は ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。