---
title: "コンパイラ エラー C2693 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2693"
ms.assetid: b7364ca8-b6be-48c0-97d6-6029787fb171
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# コンパイラ エラー C2693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': マネージ配列または WinRT 配列への参照の比較が正しくありません  
  
 どのような種類の非等値比較でも、マネージ配列または WinRT 配列はテストできません。  たとえば、マネージ配列が等しいかどうかを確認するためにテストすることはできますが、1 つの配列が別の配列より大きいか小さいかを確認するためにテストすることはできません。  
  
 **C\+\+ マネージ拡張**  
  
 どのような種類の非等値比較でも、[\_\_gc](../Topic/__gc.md) 配列はテストできません。  たとえば、マネージ配列が等しいかどうかを確認するためにテストすることはできますが、1 つの配列が別の配列より大きいか小さいかを確認するためにテストすることはできません。  
  
 次の例では C2693 が生成されます。  
  
```  
// C2693b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
int func3(int a __gc[], int b __gc[]) {  
   return a < b;    // C2693  
}  
int func1(int a __gc[], int b __gc[]) {  
   return a != b;   // OK  
}  
  
int func2(int a __gc[], int b __gc[]) {  
   return a == b;   // OK  
}  
```