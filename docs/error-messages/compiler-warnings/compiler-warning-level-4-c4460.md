---
title: "コンパイラの警告 (レベル 4) C4460 | Microsoft Docs"
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
  - "C4460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4460"
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT 演算子または CLR 演算子 'operator' は参照によって渡されたパラメーターを含んでいます。WinRT 演算子または CLR 演算子 'operator' は C\+\+ 演算子 'operator' とは異なる意味を示します。値によって渡すことを意図しましたか?  
  
 ユーザー定義の Windows ランタイム演算子または CLR 演算子に参照で値を渡しました。  値が関数内で変更された場合、関数の呼び出し後の戻り値が関数の戻り値に割り当てられることに注意してください。  標準 C\+\+ では、関数の呼び出し後、変更された値が反映されます。  
  
## 使用例  
 次の例では C4460 を生成し、その修正方法を示しています。  
  
```  
// C4460.cpp  
// compile with: /W4 /clr   
#include <stdio.h>  
  
public value struct V {  
   static V operator ++(V& me) {   // C4460  
   // try the following line instead  
   // static V operator ++(V me) {  
  
      printf_s(__FUNCSIG__ " called\n");  
      V tmp = me;  
      me.m_i++;  
      return tmp;  
   }  
   int m_i;  
};  
  
int main() {  
   V v;  
   v.m_i = 0;  
  
   printf_s("%d\n", v.m_i);   // Should print 0  
   v++;   // Translates to "v = V::operator ++(v)"  
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning  
}  
```