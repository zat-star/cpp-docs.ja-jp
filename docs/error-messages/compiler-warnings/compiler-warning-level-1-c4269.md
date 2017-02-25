---
title: "コンパイラの警告 (レベル 1) C4269 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4269"
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : コンパイラが生成した既定のコンストラクターでの 'const' 自動データ初期化は信頼性のない結果を生じます。  
  
 非単純クラスの **const** 自動インスタンスは、コンパイラが生成した既定のコンストラクターで初期化されます。  
  
## 使用例  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 このクラスのインスタンスはスタック上に生成されるため、`m_data` の初期値は何でもかまいません。  また、**const** インスタンスであるため、`m_data` の値は変更できません。