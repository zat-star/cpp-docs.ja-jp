---
title: "UnorderedMap::UnorderedMap コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::UnorderedMap"
ms.assetid: bd62e663-7f3a-43ef-ad6d-8266128c778b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::UnorderedMap コンストラクター
UnorderedMap クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```scr  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
#### パラメーター  
 `InIt`  
 現在の UnorderedMap の型名。  
  
 `P`  
 2 つのキーを比較してそれらが等しいかどうかを判定できる関数オブジェクト。 このパラメーターの既定値は [std::equal\_to\<K\>](../standard-library/equal-to-struct.md) です。  
  
 `H`  
 キーのハッシュ値を生成する関数オブジェクト。 このパラメーターの既定値は、そのクラスがサポートするキーの型の [hash クラス](../Topic/hash%20Class%201.md) です。  
  
 `m`  
 現在の UnorderedMap を初期化するために使用される [std::unordered\_map](../standard-library/unordered-map-class.md) への参照または [左辺値と右辺値](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)。  
  
 il  
 マップを初期化するために使用される [std::pair](../standard-library/initializer-list-class.md) オブジェクトの [std::initializer\_list](../standard-library/pair-structure.md)。  
  
 `first`  
 現在の UnorderedMap を初期化するために使用される要素の範囲内の最初の要素の入力反復子。  
  
 `last`  
 現在の UnorderedMap を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections 名前空間](../cppcx/platform-collections-namespace.md)   
 [コレクション](../cppcx/collections-c-cx.md)