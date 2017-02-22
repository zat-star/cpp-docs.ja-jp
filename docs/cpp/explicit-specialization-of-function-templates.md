---
title: "関数テンプレートの明示的特殊化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言 (関数を), 関数テンプレートの特殊化"
  - "関数テンプレートの明示的特殊化"
  - "関数テンプレート, 特殊化"
  - "オーバーライド, 関数"
  - "関数テンプレートの特殊化"
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 関数テンプレートの明示的特殊化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数テンプレートを使用すると、特定の型のために関数テンプレートの明示的な特殊化 \(オーバーライド\) を提供することによって、その型の特別な動作を定義できます。  次に例を示します。  
  
```  
template<> void MySwap(double a, double b);  
```  
  
 この宣言によって、**double** の変数用に、別の関数を定義できます。  非テンプレート関数と同様、標準データ型変換 \(変数の **float** 型から **double** への上位変換など\) が適用されます。  
  
## 使用例  
  
```  
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## 参照  
 [関数テンプレート](../cpp/function-templates.md)