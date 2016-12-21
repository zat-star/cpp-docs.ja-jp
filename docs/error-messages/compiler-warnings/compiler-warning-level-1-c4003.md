---
title: "コンパイラの警告 (レベル 1) C4003 | Microsoft Docs"
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
  - "C4003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4003"
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マクロ '識別子' に指定された実引数の数が少なすぎます。  
  
 マクロ定義にある仮パラメーターの数が、マクロの実パラメーターの数を超えています。  マクロの展開では、不足しているパラメーターに空のテキストが代入されます。  
  
 次の例では警告 C4003 が生成されます。  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```