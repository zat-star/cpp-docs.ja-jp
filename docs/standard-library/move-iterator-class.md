---
title: "move_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.move_iterator"
  - "move_iterator"
  - "iterator/std::move_iterator"
  - "std::move_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "move_iterator クラス"
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# move_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス テンプレート `move_iterator` は反復子のラッパーです。  move\_iterator は、ラップする \(格納する\) 反復子と同じ動作を提供します。ただし、格納されている反復子の逆参照演算子を右辺値参照に変換して、コピーを移動を切り替えます。  右辺値の詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
## 構文  
  
```  
template<class Iterator>  
    class move_iterator {  
public:  
    typedef Iterator iterator_type;  
    typedef typename      
        iterator_traits<Iterator>::iterator_category  
            iterator_category;  
    typedef typename iterator_traits<Iterator>::value_type  
        value_type;  
    typedef typename iterator_traits<Iterator>::difference_type  
        difference_type;  
    typedef Iterator  
        pointer;  
    typedef value_type&&  
        reference;  
  
    move_iterator();  
    explicit move_iterator (Iterator right);  
    template<class Type>  
        move_iterator (const move_iterator<Type>& right);  
    template <class Type>   
        move_iterator& operator=(const move_iterator<Type>& right);  
  
    iterator_type base () const;  
    reference operator* () const;  
    pointer operator-> () const;  
  
    move_iterator& operator++ ();  
    move_iterator operator++ (int);  
    move_iterator& operator-- ();  
    move_iterator operator-- (int);  
  
    move_iterator& operator+= (difference_type off);  
    move_iterator operator+ (difference_type off) const;  
    move_iterator& operator-= (difference_type off);  
    move_iterator operator- (difference_type off) const;  
    reference operator[] (difference_type off) const;  
    };  
```  
  
## 解説  
 このテンプレート クラスは、逆参照時以外は反復子のように動作するオブジェクトを表します。  これは、メンバー関数 `base``()` を介してアクセスされる `Iterator` 型のランダム アクセス反復子を格納します。  `move_iterator` に対するすべての操作は、格納されている反復子で直接実行されます。ただし、`operator*` の結果は、`value_type&&` に暗黙的にキャストされ、右辺値参照が作成されます。  
  
 `move_iterator` は、ラップされた反復子で定義されていない操作が可能である場合があります。  これらの操作は使用しないでください。  
  
### コンストラクター  
  
|||  
|-|-|  
|[move\_iterator](../Topic/move_iterator::move_iterator.md)|`move_iterator` 型のオブジェクトのコンストラクター。|  
  
### Typedef  
  
|||  
|-|-|  
|[move\_iterator::iterator\_type](../Topic/move_iterator::iterator_type.md)|テンプレート パラメーター `RandomIterator` のシノニム。|  
|[move\_iterator::iterator\_category](../Topic/move_iterator::iterator_category.md)|同じ名前の長い `typename` 式のシノニム、`iterator_category` は反復子の汎用機能を識別します。|  
|[move\_iterator::value\_type](../Topic/move_iterator::value_type.md)|同じ名前の長い `typename` 式のシノニム、`value_type` は反復子要素の型を表します。|  
|[move\_iterator::difference\_type](../Topic/move_iterator::difference_type.md)|同じ名前の長い `typename` 式のシノニム、`difference_type` は要素の差分値を表すために必要な整数型を表します。|  
|[move\_iterator::pointer](../Topic/move_iterator::pointer.md)|テンプレート パラメーター `RandomIterator` のシノニム。|  
|[move\_iterator::reference](../Topic/move_iterator::reference.md)|`rvalue` 参照 `value_type&&` のシノニム。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[move\_iterator::base](../Topic/move_iterator::base.md)|このメンバー関数は、この `move_iterator` によってラップされた、格納されている反復子を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[move\_iterator::operator\*](../Topic/move_iterator::operator*.md)|`(reference)*` `base` `().` を返します。|  
|[move\_iterator::operator\+\+](../Topic/move_iterator::operator++.md)|格納されている反復子をインクリメントします。  実際の動作は、前置インクリメント操作であるか、後置インクリメント操作であるかによって異なります。|  
|[move\_iterator::operator\-\-](../Topic/move_iterator::operator--.md)|格納されている反復子をデクリメントします。  実際の動作は、前置インクリメント操作であるか、後置インクリメント操作であるかによって異なります。|  
|[move\_iterator::operator\-\>](../Topic/move_iterator::operator-%3E.md)|`&**this` を返します。|  
|[move\_iterator::operator\-](../Topic/move_iterator::operator-.md)|最初に現在位置から右側の値を減算することによって `move_iterator(*this) -=`  を返します。|  
|[move\_iterator::operator](../Topic/move_iterator::operator.md)|`(reference)*(*this + off)` を返します。  現在のベースからのオフセットを指定し、その位置の値を取得できます。|  
|[move\_iterator::operator\+](../Topic/move_iterator::operator+.md)|`move_iterator(*this) +=`  値を返します。  ベースにオフセットを加算し、その位置の値を取得できます。|  
|[move\_iterator::operator\+\=](../Topic/move_iterator::operator+=.md)|右辺値を格納されている反復子に加算し、`*this` を返します。|  
|[move\_iterator::operator\-\=](../Topic/move_iterator::operator-=.md)|右辺値を格納されている反復子から減算し、`*this` を返します。|  
  
## 必要条件  
 **ヘッダー:**\<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [左辺値と右辺値](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)   
 [移動コンストラクターと移動代入演算子 \(C\+\+\)](../Topic/Move%20Constructors%20and%20Move%20Assignment%20Operators%20\(C++\).md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)