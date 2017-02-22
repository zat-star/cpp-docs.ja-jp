---
title: "コンパイラの警告 (レベル 1) C4377 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4377"
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラの警告 (レベル 1) C4377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ネイティブ型は、既定値がプライベートに指定されています。\-d1PrivateNativeTypes は使用できません  
  
 以前のリリースでは、アセンブリのネイティブ型は既定ではパブリックであり、それらをプライベートにするために内部の非公開コンパイラ オプション \(**\/d1PrivateNativeTypes**\) が使用されていました。  
  
 現在は、ネイティブおよび CLR を含むすべての型は、アセンブリ内で既定でプライベートになっているので、**\/d1PrivateNativeTypes** は不要になりました。  
  
## 使用例  
 次の例では C4377 エラーが生成されます。  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```