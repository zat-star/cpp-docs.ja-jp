---
title: "UnorderedMapView::UnorderedMapView コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::UnorderedMapView"
ms.assetid: 408aa6ca-dd8d-4946-a817-42a31d19f429
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::UnorderedMapView コンストラクター
UnorderedMapView クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
UnorderedMapView();  
  
explicit UnorderedMapView(size_t n);  
  
UnorderedMapView(size_t n, const H& h);  
  
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m  
    );  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
  
UnorderedMapView(  
    std::initializer_list<std::pair<const K, V>> il  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
```  
  
#### パラメーター  
 n  
 領域を事前に割り当てる要素の数。  
  
 `InIt`  
 UnorderedMapView の型名。  
  
 `H`  
 キーのハッシュ値にできる関数オブジェクト。 既定値は、`std::hash` でサポートされる型の [std::hash\<K\>](http://msdn.microsoft.com/ja-jp/54f67435-af9d-4217-a29d-fa4d2491a104) です。  
  
 `P`  
 2 つのキーを比較して等価性を確認できる関数オブジェクトを提供する型。 既定値は [std::equal\_to\<K\>](../standard-library/equal-to-struct.md) です。  
  
 `m`  
 UnorderedMapView を初期化するために使用される [std::unordered\_map](../standard-library/unordered-map-class.md) への参照または [左辺値と右辺値](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf)。  
  
 `first`  
 UnorderedMapView を初期化するために使用される要素の範囲内の最初の要素の入力反復子。  
  
 `last`  
 UnorderedMapView を初期化するために使用される要素の範囲の後の最初の要素の入力反復子。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::UnorderedMapView クラス](../cppcx/platform-collections-unorderedmapview-class.md)