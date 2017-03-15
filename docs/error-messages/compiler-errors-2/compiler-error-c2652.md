---
title: "コンパイラ エラー C2652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2652"
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : コピー コンストラクターの第 1 パラメーターが、'identifier' であってはなりません。  
  
 コピー コンストラクターの 1 番目のパラメーターは、このコピー コンストラクターを使うクラス、構造体、または共用体と同じ型になっています。  1 番目のパラメーターには型への参照を指定できますが、型自体は指定できません。  
  
 次の例では警告 C2651 が生成されます。  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```