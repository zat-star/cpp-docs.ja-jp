---
title: "コンパイラの警告 (レベル 1) C4716 | Microsoft Docs"
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
  - "C4716"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4716"
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4716
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 関数には戻り値が必要です。  
  
 指定された関数は値を返しませんでした。  
  
 関数の戻り値の型が void の場合だけ、戻り値を伴わない return コマンドを使用できます。  
  
 この関数を呼び出すと、未定義の値が返されます。  
  
 この警告は、自動的にエラーになります。  この動作を変更する場合は、[warning](../../preprocessor/warning.md) を使用します。  
  
 次の例では警告 C4716 が生成されます。  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```