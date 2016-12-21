---
title: "コンパイラ エラー C3610 | Microsoft Docs"
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
  - "C3610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3610"
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'valuetype' : メソッド 'method' を呼び出すには、値の型を 'ボックス' する必要があります。  
  
 既定では、値型はマネージ ヒープにはありません。  `Object` など、.NET ランタイム クラスからメソッドを呼び出すには、値型をマネージ ヒープに移動する必要があります。  
  
 C3610 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では警告 C3610 が生成されます。  
  
```  
// C3610.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class A {};  
  
int main() {  
   A a;  
   a.GetType(); // C3610  
  
   // OK  
   __box A* ovar = __box(a);  
   ovar->GetType();  
}  
```