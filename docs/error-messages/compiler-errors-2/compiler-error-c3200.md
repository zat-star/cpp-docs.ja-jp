---
title: "コンパイラ エラー C3200 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3200"
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template' : テンプレート パラメーター 'parameter' に対する無効なテンプレート引数です。クラス テンプレートが必要です。  
  
 クラス テンプレートに渡された引数が無効です。  クラス テンプレートには、パラメーターとしてテンプレートを渡す必要があります。  次の例では、`Y<int, int> aY` の呼び出しによって C3200 が生成されます。  最初のパラメーターは、`Y<X, int> aY` などのテンプレートにする必要があります。  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```