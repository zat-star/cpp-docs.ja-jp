---
title: "コンパイラ エラー C2450 | Microsoft Docs"
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
  - "C2450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2450"
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

switch 式の求める数値の型 'type' が不正です。  
  
 `switch` の式の評価結果が無効な型になります。  switch の式は、整数型または整数型へのあいまいでない変換を持つクラス型に評価される必要があります。  評価結果がユーザー定義型になる場合は、変換演算子を指定する必要があります。  
  
 次の例では警告 C2450 が生成されます。  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```