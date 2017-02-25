---
title: "コンパイラ エラー C2470 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2470"
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C2470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 関数定義のようですが、パラメーター リストがありません。外見上の本体をスキップします。  
  
 関数定義に引数リストが指定されていません。  
  
 次の例では警告 C2470 が生成されます。  
  
```  
// C2470.cpp  
int MyFunc {};  // C2470  
void MyFunc2() {};  //OK  
  
int main(){  
   MyFunc();  
   MyFunc2();  
}  
```