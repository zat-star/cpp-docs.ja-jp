---
title: "match_results クラス | Microsoft Docs"
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
  - "std.tr1.match_results"
  - "match_results"
  - "std::tr1::match_results"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "match_results クラス [TR1]"
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
caps.latest.revision: 16
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# match_results クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サブマッチのシーケンスを保持します。  
  
## 構文  
  
```  
template<class BidIt,  
    class Alloc = allocator<typename iterator_traits<BidIt>::value_type> >  
    class match_results {  
public:  
    explicit match_results(const Alloc& alloc = Alloc());  
    match_results(const match_results& right);  
  
    match_results& operator=(const match_results& right);  
  
    difference_type position(size_type sub = 0) const;  
    difference_type length(size_type sub = 0) const;  
    string_type str(size_type sub = 0) const;  
    const_reference operator[](size_type n) const;  
  
    const_reference prefix() const;  
    const_reference suffix() const;  
    const_iterator begin() const;  
    const_iterator end() const;  
  
    template<class OutIt>  
        OutIt format(OutIt out,  
            const string_type& fmt, match_flag_type flags = format_default) const;  
    string_type format(const string_type& fmt,  
        match_flag_type flags = format_default) const;  
  
    allocator_type get_allocator() const;  
    void swap(const match_results& other) throw();  
  
    size_type size() const;  
    size_type max_size() const;  
    bool empty() const;  
  
    typedef sub_match<BidIt> value_type;  
    typedef const typename Alloc::const_reference const_reference;  
    typedef const_reference reference;  
    typedef T0 const_iterator;  
    typedef const_iterator iterator;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef typename Alloc::size_type size_type;  
    typedef Alloc allocator_type;  
    typedef typename iterator_traits<BidIt>::value_type char_type;  
    typedef basic_string<char_type> string_type;  
    };  
```  
  
#### パラメーター  
 `BidIt`  
 サブマッチ用の反復子の型。  
  
 `Alloc`  
 ストレージを管理するためのアロケーターの型です。  
  
## 解説  
 このテンプレート クラスは、正規表現の検索で生成された `sub_match<BidIt>` 型の要素の変更不可能なシーケンスを制御するオブジェクトを表します。 各要素は、それに対応するキャプチャ グループと一致したサブシーケンスを指します。  
  
## 必要条件  
 **ヘッダー:** \<regex\>  
  
 **名前空間:** std  
  
## 参照  
 [\<regex\>](../standard-library/regex.md)