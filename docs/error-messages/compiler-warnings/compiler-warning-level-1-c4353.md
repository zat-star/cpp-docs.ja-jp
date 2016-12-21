---
title: "コンパイラの警告 (レベル 1) C4353 | Microsoft Docs"
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
  - "C4353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4353"
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能の使用 : 関数式として定数 0 が使用されています。本来の '\_\_noop' 関数を使用してください。  
  
 定数ゼロ \(0\) は関数の式として使用できません。  詳細については、「[\_\_noop](../../intrinsics/noop.md)」を参照してください。  
  
 次の例では警告 C4353 が生成されます。  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```