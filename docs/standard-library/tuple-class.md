---
title: "tuple クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::tuple"
  - "std.tr1.tuple"
  - "tuple"
  - "tr1.tuple"
  - "std::tr1::tuple"
  - "tuple/std::tr1::tuple"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple クラス"
  - "tuple クラス [TR1]"
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

固定長の要素シーケンスをラップします。  
  
## 構文  
  
```  
template<class T1, class T2, ..., class TN>  
class tuple {  
public:  
    tuple();  
    explicit tuple(P1, P2, ..., PN);              // 0 < N  
    tuple(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple(const pair<U1, U2>&);               // N == 2  
    void swap(tuple& right);  
    tuple& operator=(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple& operator=(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple& operator=(const pair<U1, U2>&);    // N == 2  
    };  
```  
  
#### パラメーター  
 `TN`  
 N 番目の組 \(tuple\) 要素の型。  
  
## 解説  
 このテンプレート クラスは、`T1` 型、`T2` 型、...、`TN` 型の N 個のオブジェクトを格納するオブジェクトを表します \(`0 <= N <= Nmax`\)。  組のインスタンス `tuple<T1, T2, ..., TN>` のエクステントは、テンプレートの引数番号 `N` に相当します。  テンプレートの引数 `Ti` およびその型の対応する値 \(格納されている値\) の実際のインデックスは、`i - 1` になります。  したがって、このドキュメントでは型に 1 ～ N の番号を振っていますが、対応するインデックス値の範囲は 0 ～ N \- 1 になります。  
  
## 使用例  
  
```  
// tuple.cpp  
// compile with: /EHsc  
  
#include <vector>  
#include <iomanip>  
#include <iostream>  
#include <tuple>  
#include <string>  
  
using namespace std;  
  
typedef tuple <int, double, string> ids;  
  
void print_ids(const ids& i)  
{  
   cout << "( "  
        << get<0>(i) << ", "   
        << get<1>(i) << ", "   
        << get<2>(i) << " )." << endl;  
}  
  
int main( )  
{  
   // Using the constructor to declare and initialize a tuple  
   ids p1(10, 1.1e-2, "one");  
  
   // Compare using the helper function to declare and initialize a tuple  
   ids p2;  
   p2 = make_tuple(10, 2.22e-1, "two");  
  
   // Making a copy of a tuple  
   ids p3(p1);  
  
   cout.precision(3);  
   cout << "The tuple p1 is: ( ";  
   print_ids(p1);  
   cout << "The tuple p2 is: ( ";  
   print_ids(p2);  
   cout << "The tuple p3 is: ( ";  
   print_ids(p3);  
  
   vector<ids> v;  
  
   v.push_back(p1);  
   v.push_back(p2);  
   v.push_back(make_tuple(3, 3.3e-2, "three"));  
  
   cout << "The tuples in the vector are" << endl;  
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)  
   {  
      print_ids(*i);  
   }  
}  
```  
  
  **タプル p1 は次の操作: \(10、0.011、1\)。**  
**タプル p2 が次の操作: \(10、0.222、2\)。**  
**タプル p3 は次の操作: \(10、0.011、1\)。**  
**ベクターのセットがあります。**  
**\(10、0.011、1\)。**  
**\(10、0.222、2\)。**  
**\(3、0.033、3\)。**   
## 必要条件  
 **ヘッダー:** の \<タプル\>  
  
 **名前空間:** std  
  
## 参照  
 [\<tuple\>](../standard-library/tuple.md)   
 [make\_tuple 関数](../Topic/make_tuple%20Function.md)