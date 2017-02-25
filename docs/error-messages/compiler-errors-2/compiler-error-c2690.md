---
title: "コンパイラ エラー C2690 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2690"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2690"
ms.assetid: f165a806-14bd-4942-99b7-8a9fc7dea227
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# コンパイラ エラー C2690
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': マネージ配列または WinRT 配列に対してポインターの算術演算を実行することはできません  
  
 マネージ配列または WinRT 配列では、ポインターの算術演算は許可されません。  配列インデックス表記を使用して配列を走査します。  
  
 **C\+\+ マネージ拡張**  
  
 [\_\_gc](../Topic/__gc.md) 配列では、ポインターの算術演算は許可されません。  配列インデックス表記を使用して配列を走査します。  
  
 次の例では C2690 が生成されます。  
  
```  
// C2690b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   String* x[] = new String*[10];  
   x[0] = "test";  
   Console::WriteLine(x[0]);  
   x++;   // C2690  
}  
```