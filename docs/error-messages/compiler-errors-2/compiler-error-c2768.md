---
title: "コンパイラ エラー C2768 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2768"
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 明示的なテンプレート引数を使用することはできません。  
  
 コンパイラは、関数定義が関数テンプレートの明示的な特化であると想定されたのか、または関数定義が新しい関数に対する定義であると想定されたのかを判断できませんでした。  
  
 このエラーは、コンパイラ準拠拡張機能の一部として、Visual Studio .NET 2003 に導入されました。  
  
 次の例では警告 C2768 が生成されます。  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```