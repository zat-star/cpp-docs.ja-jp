---
title: "C++ での宣言の位置 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言のポインター"
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ での宣言の位置
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

名前は宣言子の直後、ただし初期化子 \(省略可能\) よりも前の位置で宣言されるものと見なされます   \(宣言子の詳細については、「[宣言子](http://msdn.microsoft.com/ja-jp/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)」を参照\)。  
  
 次の例について考えます。  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 仮に、宣言の位置が初期化より "後" であれば、ローカル  *は 7.0 \(グローバル変数 `dVar` の値\) に初期化されます。`dVar`* しかし、実際にはそうでないため、`dVar` は未定義の値に初期化されます。  
  
## 参照  
 [スコープ](../cpp/scope-visual-cpp.md)