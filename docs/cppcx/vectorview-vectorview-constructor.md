---
title: "VectorView::VectorView コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::VectorView コンストラクター"
ms.assetid: 5ec14dbc-5f6f-44b6-8fc4-f5a31053eb5f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::VectorView コンストラクター
VectorView クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
#### パラメーター  
 `InIt`  
 現在の VectorView を初期化するために使用されるオブジェクトのコレクションの型。  
  
 il  
 VectorView を初期化するために要素が使用される [std::initializer\_list](../standard-library/initializer-list-class.md)。  
  
 `N`  
 現在の VectorView を初期化するために使用されるオブジェクトのコレクションの要素数。  
  
 `size`  
 VectorView の要素数。  
  
 `value`  
 現在の VectorView の各要素を初期化するために使用される値。  
  
 `v`  
 現在の VectorView を初期化するために使用される [::std::vector](../Topic/vector%20Class%201.md) への [左辺値と右辺値](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)。  
  
 `ptr`  
 現在の VectorView を初期化するために使用される `std::vector` へのポインター。  
  
 `arr`  
 現在の VectorView を初期化するために使用される [Platform::Array](../cppcx/platform-array-class.md) オブジェクト。  
  
 `a`  
 現在の VectorView を初期化するために使用される [std::array](../Topic/vector%20Class%201.md) オブジェクト。  
  
 `first`  
 現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最初の要素。`first` の型は*完全転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md)」を参照してください。  
  
 `last`  
 現在の VectorView を初期化するために使用されるオブジェクトのシーケンスの最後の要素。`last` の型は*完全転送*によって渡されます。 詳細については、「[右辺値参照宣言子: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
## 参照  
 [Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)