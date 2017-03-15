---
title: "添字演算子 | Microsoft Docs"
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
  - "配列 [C++], 添字"
  - "演算子のオーバーロード, 例"
  - "演算子 [C++], オーバーロード"
  - "添字演算子"
  - "添字演算子, オーバーロード"
  - "添字"
ms.assetid: eb151281-6733-401d-9787-39ab6754c62c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 添字演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数呼び出し演算子など、添字演算子 \(**\[ \]**\) は、二項演算子と見なされます。  添字演算子は 1 つの引数を受け取る非静的メンバー関数である必要があります。  この引数は任意の型にでき、目的の配列の添字を指定します。  
  
## 使用例  
 範囲チェックを実行する型 `int` のベクターを作成する方法を次の例に示します。  
  
```  
// subscripting.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class IntVector {  
public:  
   IntVector( int cElements );  
   ~IntVector() { delete [] _iElements; }  
   int& operator[](int nSubscript);  
private:  
   int *_iElements;  
   int _iUpperBound;  
};  
  
// Construct an IntVector.  
IntVector::IntVector( int cElements ) {  
   _iElements = new int[cElements];  
   _iUpperBound = cElements;  
}  
  
// Subscript operator for IntVector.  
int& IntVector::operator[](int nSubscript) {  
   static int iErr = -1;  
  
   if( nSubscript >= 0 && nSubscript < _iUpperBound )  
      return _iElements[nSubscript];  
   else {  
      clog << "Array bounds violation." << endl;  
      return iErr;  
   }  
}  
  
// Test the IntVector class.  
int main() {  
   IntVector v( 10 );  
   int i;  
  
   for( i = 0; i <= 10; ++i )  
      v[i] = i;  
  
   v[3] = v[9];  
  
   for ( i = 0; i <= 10; ++i )  
      cout << "Element: [" << i << "] = " << v[i] << endl;  
}  
```  
  
  **配列の範囲違反。**  
**Element: \[0\] \= 0**  
**Element: \[1\] \= 1**  
**Element: \[2\] \= 2**  
**Element: \[3\] \= 9**  
**Element: \[4\] \= 4**  
**Element: \[5\] \= 5**  
**Element: \[6\] \= 6**  
**Element: \[7\] \= 7**  
**Element: \[8\] \= 8**  
**Element: \[9\] \= 9**  
**配列の範囲違反。**  
**Element: \[10\] \= 10**   
## コメント  
 前のプログラムで `i` が 10 に達すると、`operator[]` は境界外の添字が使用されていることを検出して、エラー メッセージを発行します。  
  
 関数 `operator[]` は参照型を返すことに注意してください。  これにより、これが左辺値になり、代入演算子の両側で添字式を使用できるようになります。  
  
## 参照  
 [演算子のオーバーロード](../cpp/operator-overloading.md)