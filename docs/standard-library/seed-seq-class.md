---
title: seed_seq クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::seed_seq
- random/std::seed_seq::result_type
- random/std::seed_seq::generate
- random/std::seed_seq::size
- random/std::seed_seq::param
dev_langs:
- C++
helpviewer_keywords:
- std::seed_seq [C++]
- std::seed_seq [C++], result_type
- std::seed_seq [C++], generate
- std::seed_seq [C++], size
- std::seed_seq [C++], param
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c55680fd4558292ef06204c937050b9fe5ac555
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="seedseq-class"></a>seed_seq Class

乱数エンジンにランダム化されたシードを提供できる符号なし整数値のベクターを格納します。

## <a name="syntax"></a>構文

```cpp
class seed_seq
   {
public:
   // types
   typedef unsigned int result_type;

   // constructors
   seed_seq();
   template <class T>
      seed_seq(initializer_list<T> initlist);
   template <class InputIterator>
      seed_seq(InputIterator begin, InputIterator end);

   // generating functions
   template <class RandomAccessIterator>
      void generate(RandomAccessIterator begin, RandomAccessIterator end);

   // property functions
   size_t size() const;
   template <class OutputIterator>
      void param(OutputIterator dest) const;

   // no copy functions
   seed_seq(const seed_seq&) = delete;
   void operator=(const seed_seq&) = delete;
   };
```

## <a name="types"></a>種類

`typedef unsigned int result_type;` シード シーケンスの要素の型。 32 ビット符号なし整数型。

## <a name="constructors"></a>コンストラクター

`seed_seq();` 既定のコンス トラクターに空の内部シーケンスを初期化します。

`template<class T>` `seed_seq(initializer_list<T> initlist);` 使用して`initlist`内部シーケンスを設定します。
`T` は整数型である必要があります。

`template<class InputIterator>` `seed_seq(InputIterator begin, InputIterator end);` 指定された入力反復子の範囲内のすべての要素を使用して、内部シーケンスを初期化します。
`iterator_traits<InputIterator>::value_type` は整数型である必要があります。

## <a name="members"></a>メンバー

### <a name="generating-functions"></a>関数の生成

`template<class RandomAccessIterator> void generate(RandomAccessIterator begin,          RandomAccessIterator end);` 内部アルゴリズムを使用して、指定されたシーケンスの要素を追加します。 このアルゴリズムは、`seed_seq` が初期化された内部シーケンスによって影響を受けます。
`begin == end` の場合は何も処理しません。

### <a name="property-functions"></a>プロパティ関数

`size_t size() const;` 内の要素の数を返します、`seed_seq`です。

`template<class OutputIterator> void param(OutputIterator dest) const;` 出力反復子に内部シーケンスをコピー`dest`です。

## <a name="example"></a>例

次のコード例は、3 つのコンストラクターを実行し、配列に割り当てられたときに結果の `seed_seq` インスタンスから出力を生成します。 `seed_seq` を乱数ジェネレーターで使用する例については、「[\<random>](../standard-library/random.md)」をご覧ください。

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

```Output
seed_seq::size(): 0
seed_seq::param():
Generating a sequence of 5 elements into an array:
505382999
163489202
3932644188
763126080
73937346

seed_seq::size(): 3
seed_seq::param(): 1701 1729 1791
Generating a sequence of 5 elements into an array:
1730669648
1954224479
2809786021
1172893117
2393473414

seed_seq::size(): 7
seed_seq::param(): 65 32 66 32 67 32 68
Generating a sequence of 5 elements into an array:
3139879222
3775111734
1084804564
2485037668
1985355432
```

## <a name="remarks"></a>コメント

このクラスのメンバー関数は例外をスローしません。

## <a name="requirements"></a>要件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
