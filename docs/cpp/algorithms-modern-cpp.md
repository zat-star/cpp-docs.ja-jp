---
title: "アルゴリズム (Modern C++) | Microsoft Docs"
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
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アルゴリズム (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最新 C\+\+ プログラミングでは、[標準テンプレート ライブラリ](../standard-library/cpp-standard-library-reference.md) \(STL\) のアルゴリズムを使用することをお勧めします。  次に重要な例を示します。  
  
-   既定の走査アルゴリズムである `for_each` \(また、not\-in\-place セマンティクスの `transform`\)。  
  
-   既定の検索アルゴリズムである `find_if`。  
  
-   `sort`、`lower_bound`、およびその他の既定の並べ替えアルゴリズムや検索アルゴリズム。  
  
 比較子を記述するには、厳密な `<` を使用し、可能な場合は、*名前付きラムダ*を使用します。  
  
```cpp  
  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
  
```  
  
## ループ  
 可能な場合は、手動で記述したループではなく、範囲ベースの `for` ループまたはアルゴリズム呼び出しを使用します。  `copy`、`transform`、`count_if`、`remove_if` などは、それらの意図が明確であり、バグのないコードを作成しやすいため、手動で記述したループよりはるかに優れています。  また、多くの STL アルゴリズムは実装が最適化されているため、より効率的です。  
  
 次のような従来の C\+\+ を使用する代わりに、  
  
```cpp  
  
for( auto i = strings.begin(); i != strings.end(); ++i ) {  
  :::  
  :::  
}  
  
auto i = v.begin();  
  
for( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
  
```  
  
 次のような最新の C\+\+ を使用してください。  
  
```cpp  
  
for_each( begin(strings), end(strings), [](string& s) {  
  :::  
  :::  
} );  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; }  );  
  
```  
  
### 範囲ベースの for ループ  
 範囲ベースの `for` ループは、C\+\+11 言語の機能であり、STL アルゴリズムではありません。  しかし、ループに関するこの説明と併せて理解すると便利です。  範囲ベースの `for` ループは、`for` キーワードの拡張機能であり、値の範囲にわたって処理を反復するループを効率的に作成できます。  範囲ベースの `for` ループでは、STL コンテナー、文字列、および配列があらかじめ用意されています。  この新しいイテレーション構文をユーザー定義型に対して有効にするには、次のサポートを追加します。  
  
-   反復子を構造体の先頭に返す `end` メソッドと、反復子を構造体の末尾に返す `begin` メソッド。  
  
-   反復子での `operator*`、`operator!=`、および `operator++` \(前置バージョン\) の各メソッドのサポート。  
  
 これらのメソッドは、メンバー関数かスタンドアロン関数のいずれかです。  
  
## 乱数  
 従来の CRT の `rand()` 関数に多くの欠陥があることは広く知られた事実であり、C\+\+ コミュニティで長年にわたって議論されてきました。  最新の C\+\+ では、これらの欠陥に対処する必要はありません。また [\<random\>](../standard-library/random.md) に示すように、一様に分布した乱数をすばやく簡単に作成するツールが STL に用意されているので、ジェネレーターを独自に作成する必要もありません。  
  
## 参照  
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)