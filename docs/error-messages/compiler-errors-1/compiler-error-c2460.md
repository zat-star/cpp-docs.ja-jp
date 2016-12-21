---
title: "コンパイラ エラー C2460 | Microsoft Docs"
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
  - "C2460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2460"
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier2' : クラスまたは構造体は、'identifier1' で既に宣言されています。  
  
 クラスまたは構造体 \(`identifier2`\) は、それ自身のメンバー \(`identifier1`\) として宣言されています。  クラスや構造体を再帰的に定義することはできません。  
  
 次の例では警告 C2460 が生成されます。  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 代わりに、クラスでポインター参照を使用します。  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```