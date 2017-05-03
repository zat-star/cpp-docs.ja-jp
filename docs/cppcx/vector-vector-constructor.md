---
title: "Vector::Vector コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::Vector コンストラクター"
ms.assetid: 5454433d-e206-45ea-bc8b-bb5a7bf38c17
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::Vector コンストラクター
ベクター クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
Vector();  
  
explicit Vector(  
    unsigned int size  
    );  
  
Vector(  
    unsigned int size,  
    T value  
    );  
  
template <typename U> explicit Vector(  
    const ::std::vector<U>& v  
    );  
  
template <typename U> explicit Vector(  
    std::vector<U>&& v  
    );  
  
Vector(  
    const T * ptr,  
    unsigned int size  
    );  
  
template <size_t N> explicit Vector(  
    const T(&arr)[N]  
    );  
  
template <size_t N> explicit Vector(  
    const std::array<T, N>& a  
    );  
  
explicit Vector(  
    const Array<T>^ arr  
    );  
  
template <typename InIt> Vector(  
    InIt first,  
    InIt last  
    );  
  
Vector(  
    std::initializer_list<T> il  
    );  
```  
  
#### パラメーター  
 a  
 ベクターを初期化するために使用される [std::array](../standard-library/array-class-stl.md)。  
  
 a  
 ベクターを初期化するために使用される [Platform::Array](../cppcx/platform-array-class.md)。  
  
 `InIt`  
 現在のベクターを初期化するために使用されるオブジェクトのコレクションの型。  
  
 il  
 ベクターを初期化するために使用される型 `T` のオブジェクトの [std::initializer\_list](../standard-library/initializer-list-class.md)。  
  
 `N`  
 現在のベクターを初期化するために使用されるオブジェクトのコレクションの要素数。  
  
 `size`  
 ベクターの要素数。  
  
 `value`  
 現在のベクターの各要素を初期化するために使用される値。  
  
 `v`  
 現在のベクターを初期化するために使用される [std::vector](../Topic/vector%20Class%201.md) への [左辺値と右辺値](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf)。  
  
 `ptr`  
 現在のベクターを初期化するために使用される `std::vector` へのポインター。  
  
 `arr`  
 現在のベクターを初期化するために使用される [Platform::Array](../cppcx/platform-array-class.md) オブジェクト。  
  
 `a`  
 現在のベクターを初期化するために使用される [std::array](../Topic/vector%20Class%201.md) オブジェクト。  
  
 `first`  
 現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最初の要素。`first` の型は*完全転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](~/cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
 `last`  
 現在のベクターを初期化するために使用されるオブジェクトのシーケンスの最後の要素。`last` の型は*完全転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](~/cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)   
 [コレクション \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)