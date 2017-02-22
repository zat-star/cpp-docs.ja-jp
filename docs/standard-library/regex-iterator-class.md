---
title: "regex_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::regex_iterator"
  - "std.tr1.regex_iterator"
  - "regex_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_iterator クラス [TR1]"
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# regex_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一致の反復子クラス。  
  
## 構文  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef match_results<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const match_results<BidIt>* pointer;  
    typedef const match_results<BidIt>& reference;  
  
    regex_iterator();  
    regex_iterator(BidIt first, BidIt last,  
        const regex_type& re,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_iterator& right);  
    bool operator!=(const regex_iterator& right);  
    const match_results<BidIt>& operator*();  
    const match_results<BidIt> *operator->();  
    regex_iterator& operator++();  
    regex_iterator& operator++(int);  
  
    BidIt begin;                            // exposition only  
    BidIt end;                              // exposition only  
    regex_type *pregex;                     // exposition only  
    regex_constants::match_flag_type flags; // exposition only  
    match_results<BidIt> match;             // exposition only  
    };  
```  
  
#### パラメーター  
 `BidIt`  
 サブマッチの反復子の型。  
  
 `Elem`  
 一致させる要素の型。  
  
 `RXtraits`  
 要素の特徴 \(traits\) クラス。  
  
## 解説  
 このテンプレート クラスは、定数前方反復子オブジェクトを表します。 反復子範囲 `[begin, end)` で定義された文字シーケンスに正規表現オブジェクト `*pregex` を繰り返し適用することによって、`match_results<BidIt>` 型のオブジェクトを抽出します。  
  
## 例  
 正規表現の例については、以下の例をご覧ください。  
  
-   [regex\_match 関数](../Topic/regex_match%20Function.md)  
  
-   [regex\_replace 関数](../Topic/regex_replace%20Function.md)  
  
-   [regex\_search 関数](../Topic/regex_search%20Function.md)  
  
-   [swap 関数](../Topic/swap%20Function%20%3Cregex%3E.md)  
  
## 必要条件  
 **ヘッダー:** \<regex\>  
  
 **名前空間:** std  
  
## 参照  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_iterator](../standard-library/regex-iterator-class.md)