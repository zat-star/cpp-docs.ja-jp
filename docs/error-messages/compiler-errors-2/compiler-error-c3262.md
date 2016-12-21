---
title: "コンパイラ エラー C3262 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3262"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3262"
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3262
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無効な配列のインデックスです。'\#' 次元が指定されました。'\#' 次元の 'array type' が選択されています。  
  
 配列の添字が正しくありません。 インデックスの数が配列の次元数と一致しない可能性があります。  
  
 次の例では C3262 が生成されます。  
  
```  
// C3262.cpp // compile with: /clr #using <mscorlib.dll> using namespace System; #define ARRAY_SIZE 2 ref class MyClass { public: int m_i; }; // returns a multidimensional managed array of a reference type array<MyClass^, 2>^ Test0() { int i, j; array< MyClass^, 2 >^ local = new array< MyClass^, 2 > (ARRAY_SIZE, ARRAY_SIZE); for (i = 0 ; i < ARRAY_SIZE ; i++) for (j = 0 ; j < ARRAY_SIZE ; j++) { local[i][j] = new MyClass;   // C3262 // try the following line instead // local[i,j] = new MyClass; local[i,j] -> m_i = i; } return local; } int main() { int i, j; array< MyClass^, 2 >^ MyClass0; MyClass0 = Test0(); }  
```  
  
 **C\+\+ マネージ拡張**  
  
 次の例では C3262 が生成されます。  
  
```  
// C3262b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> int main() { int iArr __gc[,] = new int __gc[10,20]; iArr[1,2,3]; // C3262: 3 dimensions specified for 2-dimensional array }  
```