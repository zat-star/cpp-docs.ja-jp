---
title: "コンパイラ エラー C3632 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3632"
ms.assetid: a04e3217-f5a1-4461-a1db-d69fd096d468
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': construct のイベントの型が無効です。  
  
 [\_\_event](../../cpp/event.md) 宣言は、すべての構成要素で有効であるとは限りません。  
  
 C3632 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では警告 C3632 が生成されます。  
  
```  
// C3632.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc __interface I  
{  
   __event void sna();   // C3632  
};  
  
// use the following as an example  
__delegate void MyDel();  
public __gc __interface I2  
{  
   __event MyDel* sna;  
};  
  
int main()  
{  
}  
```