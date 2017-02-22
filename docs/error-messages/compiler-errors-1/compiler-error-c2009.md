---
title: "コンパイラ エラー C2009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2009"
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マクロの仮引数リストで '識別子' が 2 回以上使われています。  
  
 識別子がマクロ定義の仮パラメーター リスト内で 2 回以上使用されています。  マクロのパラメーター リストの識別子は一意であることが必要です。  
  
## 使用例  
 次の例では警告 C2009 が生成されます。  
  
```  
// C2009.cpp  
#include <stdio.h>  
  
#define macro1(a,a) (a*a)   // C2009  
  
int main()   
{  
    printf_s("%d\n", macro1(2));  
}  
```  
  
## 使用例  
 解決方法 :  
  
```  
// C2009b.cpp  
#include <stdio.h>  
  
#define macro2(a)   (a*a)   
#define macro3(a,b) (a*b)  
  
int main()   
{  
    printf_s("%d\n", macro2(2));  
    printf_s("%d\n", macro3(2,4));  
}  
```