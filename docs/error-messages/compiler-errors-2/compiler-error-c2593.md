---
title: "コンパイラ エラー C2593 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2593"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2593"
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2593
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator identifier' があいまいです。  
  
 オーバーロードされた演算子には、可能な演算子が 2 つ以上定義されています。  
  
 このエラーは、1 つ以上の実パラメーターで明示的なキャストを使用すると解決される場合があります。  
  
 次の例では警告 C2593 が生成されます。  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 このエラーは、`CArchive` オブジェクトを使用して浮動小数点変数をシリアル化したことが原因で発生する場合があります。  コンパイラは、演算子 `<<` があいまいであると認識します。  `CArchive` でシリアル化できる C\+\+ プリミティブ型は、固定サイズ型の `BYTE`、`WORD`、`DWORD`、および `LONG` だけです。  整数型をシリアル化するには、これらのいずれかの型にキャストする必要があります。  浮動小数点型は、`CArchive::Write()` メンバー関数を使用してアーカイブする必要があります。  
  
 浮動小数点型の変数 \(`f`\) をアーカイブ `ar` にアーカイブする例を次に示します。  
  
```  
ar.Write(&f, sizeof( float ));  
```