---
title: "コンパイラの警告 (レベル 4) C4431 | Microsoft Docs"
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
  - "C4431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4431"
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型指定子がありません \- int と仮定しました。メモ: C は、現在 int を既定値としてサポートしていません  
  
 このエラーは、Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることがあります。Visual C\+\+ は、型指定のない識別子を既定で int 型として作成しなくなりました。  識別子の型は明示的に指定する必要があります。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
## 使用例  
 次の例では C4431 エラーが生成されます。  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```