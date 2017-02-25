---
title: "コンパイラ エラー C2728 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2728"
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# コンパイラ エラー C2728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': ネイティブ配列はこの型を含むことはできません  
  
 配列作成の構文が、マネージまたは WinRT オブジェクトの配列の作成に使用されました。  ネイティブ配列の構文を使用して、マネージまたは WinRT オブジェクトの配列を作成することはできません。  
  
 詳細については、「[配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。  
  
 次の例では、C2728 を生成し、その修正方法を示しています。  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  
  
 [\_\_nogc](../../misc/nogc.md) 配列を [\_\_gc](../Topic/__gc.md) 型の配列にすることはできません。  
  
 次の例では、C2728 を生成し、その修正方法を示しています。  
  
```  
// C2728_b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
int main() {  
   int __gc* arr __nogc[5];   // C2728  
  
   // try the following line instead  
   int arr2 __gc[];  
}  
```