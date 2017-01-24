---
title: "条件式演算子 | Microsoft Docs"
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
  - "条件演算子"
  - "式 [C++], 条件"
  - "演算子 [C++], 条件"
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 条件式演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 言語では、三項演算子として条件式演算子 \(**? :**\) を使用します。  
  
## 構文  
 *conditional\-expression*:  
 *logical\-OR\-expression*  
  
 *logical\-OR expression*  **?**  *expression*  **:**  *conditional\-expression*  
  
 *logical\-OR\-expression* には、整数型、浮動小数点型、またはポインター型を指定する必要があります。  この式は、0 に等しいかどうかが評価されます。  シーケンス ポイントは *logical\-OR\-expression* に従います。  オペランドは次のように評価されます。  
  
-   *logical\-OR\-expression* が 0 でない場合、*expression* が評価されます。  この式の評価結果は、非終端の *expression* 式として与えられます  \(つまり、*logical\-OR\-expression* が true の場合のみ *expression* が評価されます\)。  
  
-   *logical\-OR\-expression* が 0 の場合、*conditional\-expression* が評価されます。  この式の結果は *conditional\-expression* の値です  \(つまり、*logical\-OR\-expression* が false の場合のみ *conditional\-expression* が評価されます\)。  
  
 *expression* または *conditional\-expression* のいずれかが評価されます。両方は評価されません。  
  
 条件演算の結果の型は、次のように、*expression* または *conditional\-expression* オペランドの型に依存します。  
  
-   *expression* または *conditional\-expression* が整数型または浮動小数点型の場合 \(それぞれ型が異なる可能性があります\)、この演算子は通常の算術変換を実行します。  結果の型は、変換後のオペランドの型です。  
  
-   *expression* と *conditional\-expression* が両方とも同じ構造体型、共用体型、またはポインター型の場合、演算結果はそれと同じ構造体型、共用体型、またはポインター型になります。  
  
-   両方のオペランドが `void` 型の場合、結果は `void` 型になります。  
  
-   一方のオペランドが任意の型のオブジェクトへのポインターであり、もう一方のオペランドが `void` へのポインターである場合、そのオブジェクトへのポインターが `void` へのポインターに変換され、結果は `void` へのポインターになります。  
  
-   *expression* または *conditional\-expression* のいずれかがポインターであり、もう一方のオペランドが値 0 の定数式である場合、結果はポインター型になります。  
  
 ポインターの型を比較する際、ポインターが指している型の型修飾子 \(**const** または `volatile`\) は重要ではありません。ただし、結果の型は、条件式を構成する両方の要素の型修飾子を継承します。  
  
## 例  
 次に、条件演算子の使用例を示します。  
  
```  
j = ( i < 0 ) ? ( -i ) : ( i );  
```  
  
 この例では、`i` の絶対値を `j` に代入します。  `i` が 0 未満の場合、`-i` が `j` に代入されます。  `i` が 0 以上の場合、`i` が `j` に代入されます。  
  
```  
void f1( void );  
void f2( void );  
int x;  
int y;  
    .  
    .  
    .  
( x == y ) ? ( f1() ) : ( f2() );  
```  
  
 この例では、2 つの関数 `f1` と `f2`、および 2 つの変数 `x` と `y` を宣言しています。  プログラムの後半では、これら 2 つの変数が同じ値の場合に `f1` 関数を呼び出します。  それ以外の場合は `f2` を呼び出します。  
  
## 参照  
 [条件演算子: ? :](../cpp/conditional-operator-q.md)