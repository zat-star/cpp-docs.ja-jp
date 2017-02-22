---
title: "コンパイラの警告 (レベル 1) C4087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4087"
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 関数のパラメーター リストは 'void' で宣言されています  
  
 関数の宣言には仮パラメーターが指定されていませんが、関数呼び出しには実パラメーターが指定されています。 余分なパラメーターは、この関数の呼び出し規則に従って渡されます。  
  
 この警告は、C コンパイラの場合に表示されます。  
  
## 使用例  
  
```  
// C4087.c // compile with: /W1 int f1( void ) { } int main() { f1( 10 );   // C4087 }  
```