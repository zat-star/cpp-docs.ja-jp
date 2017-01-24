---
title: "宣言子と変数宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "宣言子, 定義"
  - "宣言 (変数を), 宣言ステートメント"
  - "宣言 (変数を), 宣言子"
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 宣言子と変数宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このセクションの残りの部分では、次の一覧に示す変数型の宣言の形式とその意味について説明します。  特に、残りの各セクションでは、以下を宣言する方法について説明します。  
  
|変数の種類|説明|  
|-----------|--------|  
|[単純変数](../c-language/simple-variable-declarations.md)|整数型または浮動小数点型の単一値変数|  
|[配列](../Topic/Array%20Declarations.md)|同じ型の要素のコレクションで構成される変数|  
|[ポインター](../c-language/pointer-declarations.md)|他の変数をポイントし、値の代わりに変数の場所を \(アドレスの形式で\) 含む変数|  
|[列挙変数](../c-language/c-enumeration-declarations.md)|一連の名前付き整数定数の 1 つの値を保持する整数型の単純変数|  
|[構造体](../c-language/structure-declarations.md)|異なる型を持つことができる値のコレクションで構成される変数|  
|[Unions](../c-language/union-declarations.md)|同じストレージ領域を占有する異なる型の複数の値で構成される変数|  
  
 宣言子は、宣言に含まれる、プログラムに組み込まれる名前を指定する部分です。  **\*** \(ポインター\) などの修飾子と Microsoft の呼び出し規約キーワードを含めることができます。  
  
 **Microsoft 固有の仕様 →**  
  
 次のような宣言子があります。  
  
```  
__declspec(thread) char *var;  
```  
  
 `char` は型指定子、`__declspec(thread)` と `*` は修飾子、`var` は識別子の名前です。  
  
 **END Microsoft 固有の仕様**  
  
 宣言子は、値の配列、値へのポインター、および指定された型の値を返す関数を宣言するために使用します。  宣言子は、このセクションで後述する配列およびポインターの宣言に記述されます。  
  
## 構文  
 `declarator`:  
 *pointer*  opt *direct\-declarator*  
  
 *direct\-declarator*:  
 *identifier*  
  
 **\(**  *declarator*  **\)**  
  
 *direct\-declarator*  **\[**  *constant\-expression*  opt **\]**  
  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)**  
  
 *direct\-declarator*  **\(**  *identifier\-list*  opt **\)**  
  
 `pointer`:  
 **\*** *type\-qualifier\-list*  opt  
  
 **\*** *type\-qualifier\-list*  opt `pointer`  
  
 *type\-qualifier\-list*:  
 *type\-qualifier*  
  
 *type\-qualifier\-list type\-qualifier*  
  
> [!NOTE]
>  `declarator` を参照する構文については、「[Overview of Declarations \(宣言の概要\)](../Topic/Overview%20of%20Declarations.md)」または「[C 言語の構文概要](../c-language/c-language-syntax-summary.md)」にある `declaration` の構文を参照してください。  
  
 宣言子が修飾されていない識別子で構成される場合、宣言される項目は基本型を持ちます。  アスタリスク \(**\***\) が識別子の左側にある場合、型はポインター型に変更されます。  識別子の後ろに角かっこ \(**\[ \]**\) が続く場合、型は配列型に変更されます。  識別子の後ろにかっこが続く場合、型は関数型に変更されます。  宣言内での優先順位の解釈の詳細については、「[Interpreting More Complex Declarators \(さらに複雑な宣言子の解釈\)](../c-language/interpreting-more-complex-declarators.md)」を参照してください。  
  
 各宣言は 1 つ以上の識別子を宣言します。  宣言子で完全な宣言をするには、型指定子を含める必要があります。  型指定子は、配列型の要素の型、ポインター型によってアドレス指定されるオブジェクトの型、または関数の戻り値の型を示します。  
  
 [配列](../Topic/Array%20Declarations.md)と[ポインター](../c-language/pointer-declarations.md)の宣言については、このセクションの後半で詳しく説明します。  次の例に、宣言子の簡単な形式をいくつか示します。  
  
```  
int list[20]; // Declares an array of 20 int values named list  
char *cp;     // Declares a pointer to a char value  
double func( void ); // Declares a function named func, with no   
                     // arguments, that returns a double value  
int *aptr[10] // Declares an array of 10 pointers  
```  
  
 **Microsoft 固有の仕様 →**  
  
 Microsoft C コンパイラでは、数値型、構造体型、または共用体型を変更できる宣言子の数は制限されません。  数は、使用できるメモリ容量によってのみ制限されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [型の宣言](../c-language/declarations-and-types.md)