---
title: "sub_match クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sub_match"
  - "std::tr1::sub_match"
  - "std.tr1.sub_match"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sub_match クラス [TR1]"
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sub_match クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サブマッチを記述します。  
  
## 構文  
  
```  
template<class BidIt>  
    class sub_match  
        : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;  
    int compare(const value_type *right) const;  
    difference_type length() const;  
    operator basic_string<value_type>() const;  
    basic_string<value_type> str() const;  
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
    };  
```  
  
#### パラメーター  
 `BidIt`  
 サブマッチ用の反復子の型。  
  
## 解説  
 このテンプレート クラスは、[regex\_match 関数](../Topic/regex_match%20Function.md) または [regex\_search 関数](../Topic/regex_search%20Function.md) に対する呼び出しでキャプチャ グループと一致した文字のシーケンスを指定するオブジェクトを表します。[match\_results クラス](../standard-library/match-results-class.md) 型のオブジェクトは、検索に使用された正規表現内のキャプチャ グループごとに 1 つずつ、これらのオブジェクトの配列を保持します。  
  
 キャプチャ グループがオブジェクトのデータ メンバーと一致しなかった場合は、`matched` が false を保持し、2 つの反復子の `first` と `second` \(ベース `std::pair` から継承\) が等しくなります。 キャプチャ グループが一致した場合は、`matched` が true を保持し、反復子 `first` がキャプチャ グループと一致したターゲット シーケンスの最初の文字を指し、反復子 `second` がキャプチャ グループと一致したターゲット シーケンスの最後の文字の 1 つ先の位置を指します。 長さ 0 の一致の場合は、メンバー `matched` が true を保持し、2 つの反復子が等しくなり、両方が一致した位置を指します。  
  
 長さ 0 の一致は、キャプチャ グループが 1 つのアサーションのみまたは 0 回の繰り返しが許可される 1 つの繰り返しのみで構成されている場合に発生します。 例:  
  
 "^" は、ターゲット シーケンス "a" と一致します。キャプチャ グループ 0 に対応する `sub_match` オブジェクトは、両方がシーケンスの最初の文字を指す反復子を保持します。  
  
 "b\(a\*\)b" は、ターゲット シーケンス "bb" と一致します。キャプチャ グループ 1 に対応する `sub_match` オブジェクトは、両方がシーケンスの 2 つ目の文字を指す反復子を保持します。  
  
## 必要条件  
 **ヘッダー:** \<regex\>  
  
 **名前空間:** std  
  
## 参照  
 [\<regex\>](../standard-library/regex.md)   
 [sub\_match](../standard-library/sub-match-class.md)   
 [regex\_match 関数](../Topic/regex_match%20Function.md)   
 [regex\_search 関数](../Topic/regex_search%20Function.md)