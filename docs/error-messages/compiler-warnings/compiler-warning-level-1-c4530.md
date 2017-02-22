---
title: "コンパイラの警告 (レベル 1) C4530 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4530"
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 例外処理を使っていますが、アンワインド セマンティクスは有効にはなりません。\/EHsc を指定してください。  
  
 C\+\+ 例外処理を使用していますが、[\/EHsc](../../build/reference/eh-exception-handling-model.md) が選択されていません。  
  
 \/EHsc オプションが有効でない場合、スローを行う関数とスローをキャッチする関数の間のフレームにあるローカルな寿命を持つオブジェクトは破棄されません。  ただし、**try** ブロックまたは **catch** ブロックで作成されたローカルな寿命を持つオブジェクトは破棄されます。  
  
 次の例では警告 C4530 が生成されます。  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 \/EHsc を指定して例をコンパイルし、警告を解決します。