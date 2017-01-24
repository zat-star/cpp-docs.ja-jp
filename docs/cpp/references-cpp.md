---
title: "参照 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言, 参照"
  - "オブジェクト [C++], 参照"
  - "参照"
  - "参照, 宣言"
  - "参照, ポインターへの"
  - "参照 (オブジェクトを), 宣言子の構文"
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 参照 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照は、ポインターと同じように、メモリ内の他の場所に位置するオブジェクトのアドレスを格納します。  参照は、ポインターとは異なり、初期化された後で別のオブジェクトを参照するように指定したり、null に設定したりすることはできません。  参照には、左辺値参照 \(名前が付いた変数を参照する\) および右辺値参照 \([一時オブジェクト](../cpp/temporary-objects.md)を参照する\) という 2 種類の参照があります。  & 演算子は左辺値参照を示し、&& 演算子は、コンテキストによって右辺値参照またはユニバーサル参照 \(右辺値または左辺値\) を示します。  
  
 参照は次の構文を使用して宣言できます。  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 参照を指定する任意の有効な宣言子を使用できます。  参照が関数または配列型への参照でない限り、次の簡略化された構文が適用されます。  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 参照は次の順序で宣言します。  
  
 1.  宣言指定子:  
  
-   ストレージ クラスの指定子 \(省略可能\)。  
  
-   **const**\/`volatile` 修飾子 \(省略可能\)。  
  
-   型指定子: 型の名前。  
  
-   2.  宣言子:  
  
-   オプションの Microsoft 固有の修飾子。  詳細については、「[Microsoft 固有の修飾子](../Topic/Microsoft-Specific%20Modifiers.md)」を参照してください。  
  
-   & 演算子または && 演算子。  
  
-   **const**\/`volatile` 修飾子 \(省略可能\)。  
  
-   識別子。  
  
 3.  初期化子 \(省略可能\)。  
  
 配列と関数へのポインターに対するより複雑な宣言子の形式は、配列と関数の参照にも適用されます。「[ポインター](../cpp/pointers-cpp.md)」と「[宣言子](http://msdn.microsoft.com/ja-jp/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)」を参照してください。  
  
 1 つの宣言指定子の後のコンマ区切りリストに、複数の宣言子と初期化子を含めることができます。  例:  
  
```  
int &i;   
int &i, &j;   
```  
  
 次のように、参照、ポインター、およびオブジェクトをまとめて宣言できます。  
  
```  
int &ref, *ptr, k;   
```  
  
 参照は、オブジェクトのアドレスを保持しますが、構文的にはオブジェクトと同様に動作します。  
  
 次のプログラムでは、オブジェクトの名前 `Today` とオブジェクトへの参照 `TodayRef` を、プログラム内で同じように使用できることに注意してください。  
  
## 使用例  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
  **3**  
**3**  
**4**  
**4**   
## コメント  
 このセクションのトピック  
  
-   [Reference\-Type Function Arguments \(参照型関数の引数\)](../cpp/reference-type-function-arguments.md)  
  
-   [Reference\-Type Function Returns \(参照型関数の戻り値\)](../cpp/reference-type-function-returns.md)  
  
-   [References to Pointers \(ポインターへの参照\)](../cpp/references-to-pointers.md)  
  
## 参照  
 [参照の初期化](../misc/initializing-references.md)