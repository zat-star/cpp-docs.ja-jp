---
title: "コンパイラ エラー C2705 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2705"
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'label' : 'exception handler block' スコープへのジャンプが正しくありません。  
  
 実行の制御が `try`\/`catch`、`__try`\/`__except`、`__try`\/`__finally` ブロックにあるラベルに移されました。  詳細については、「[Exception Handling](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。  
  
 次の例では警告 C2705 が生成されます。  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```