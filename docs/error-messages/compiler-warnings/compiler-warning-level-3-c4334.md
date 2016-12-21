---
title: "コンパイラの警告 (レベル 3) C4334 | Microsoft Docs"
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
  - "C4334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4334"
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' : 32 ビット シフトの結果が暗黙的に 64 ビットに変換されました \(64 ビット シフトに意図的に変換しようとしましたか?\)  
  
 32 ビット シフトの結果が 64 ビットに暗黙的に型変換されましたが、コンパイラはその 64 ビット シフトが意図されていたものかどうかを判断できません。この警告を解決するには、64 ビット シフトを使用するか、シフトの結果を 64 ビットに明示的にキャストします。  
  
## 使用例  
 次の例では C4334 エラーが生成されます。  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```