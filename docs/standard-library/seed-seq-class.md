---
title: "seed_seq Class | Microsoft Docs"
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
  - "tr1::seed_seq"
  - "std::tr1::seed_seq"
  - "tr1.seed_seq"
  - "seed_seq"
  - "std.tr1.seed_seq"
  - "random/std::tr1::seed_seq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "seed_seq クラス"
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# seed_seq Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

乱数エンジンにランダム化されたシードを提供できる符号なし整数値のベクターを格納します。  
  
## 構文  
  
```  
class seed_seq  
{  
public:  
    // types  
    typedef unsigned int result_type;  
  
    // constructors  
    seed_seq();  
  
    template<class T>  
    seed_seq(initializer_list<T> initlist);  
  
    template<class InputIterator>  
    seed_seq(InputIterator begin, InputIterator end);  
  
    // generating functions  
    template<class RandomAccessIterator>  
    void generate(RandomAccessIterator begin, RandomAccessIterator end);  
  
    // property functions  
    size_t size() const;  
  
    template<class OutputIterator>  
    void param(OutputIterator dest) const;  
  
    // no copy functions  
    seed_seq(const seed_seq&) = delete;  
    void operator=(const seed_seq&) = delete;  
};  
```  
  
## 型  
 `typedef unsigned int result_type;`   
シード シーケンスの要素の型。 32 ビット符号なし整数型。  
  
## コンストラクター  
 `seed_seq();`   
既定のコンス トラクターは、空の内部シーケンスを初期化します。  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
使用して `initlist` 内部シーケンスを設定します。  
`T` 整数型である必要があります。  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
指定された入力反復子の範囲内のすべての要素を使用して、内部シーケンスを初期化します。  
`iterator_traits<InputIterator>::value_type` 整数型である必要があります。  
  
## メンバー  
  
### 関数の生成  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin, RandomAccessIterator end);`   
内部アルゴリズムを使用して、指定されたシーケンスの要素を追加します。 このアルゴリズムが使用する内部シーケンスによって影響を受ける `seed_seq` 初期化されました  
。何も場合 `begin == end`します。  
  
### プロパティ関数  
 `size_t size() const;`   
要素の数を返す、 `seed_seq`です。  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
出力反復子を内部シーケンスをコピー `dest`します。  
  
## 使用例  
 次のコード例は、3 つのコンストラクターを実行し、配列に割り当てられたときに結果の `seed_seq` インスタンスから出力を生成します。 使用例について `seed_seq` 、乱数ジェネレーターで、次を参照してください。 [\<random\>](../standard-library/random.md)します。  
  
```cpp  
#include <iostream>  
#include <random>  
#include <string>  
#include <array>  
  
using namespace std;  
  
void test(const seed_seq& sseq) {  
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;  
  
    cout << "seed_seq::param(): ";  
    ostream_iterator<unsigned int> out(cout, " ");  
    sseq.param(out);  
    cout << endl;  
  
    cout << "Generating a sequence of 5 elements into an array: " << endl;  
    array<unsigned int, 5> seq;  
    sseq.generate(seq.begin(), seq.end());  
    for (unsigned x : seq) { cout << x << endl; }  
}  
  
int main()  
{  
    seed_seq seed1;  
    test(seed1);  
  
    seed_seq seed2 = { 1701, 1729, 1791 };  
    test(seed2);  
  
    string sstr = "A B C D"; // seed string  
    seed_seq seed3(sstr.begin(), sstr.end());  
    test(seed3);  
}  
```  
  
## 出力  
  
```Output  
  
seed_seq::size(): 0 seed_seq::param(): 配列に 5 つの要素のシーケンスを生成する: 505382999 163489202 3932644188 763126080 73937346 seed_seq::size(): 3 seed_seq::param(): 1701年 1729年 1791年を配列に 5 つの要素のシーケンスを生成する: 1730669648 1954224479 2809786021 1172893117 2393473414 seed_seq::size(): 7 seed_seq::param(): 65 32 66 32 67 32 68 を配列に 5 つの要素のシーケンスを生成します。: 3139879222 3775111734 1084804564 2485037668 1985355432  
```  
  
## 解説  
 このクラスのメンバー関数は、例外をスローしません。  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)