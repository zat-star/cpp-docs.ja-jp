---
title: "コンパイラ エラー C3174 | Microsoft Docs"
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
  - "C3174"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3174"
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3174
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

モジュール属性が指定されていません。  
  
 Visual C\+\+ の属性を使用するプログラムで、属性を使用するすべてのプログラムに必要な [module](../../windows/module-cpp.md) 属性が使用されていません。  
  
 次の例では警告 C3174 が生成されます。  
  
```  
// C3174.cpp  
// C3174 expected  
// uncomment the following line to resolve this C3174  
// [module(name="x")];  
[export]  
struct S  
{  
   int i;  
};  
  
int main()  
{  
}  
```