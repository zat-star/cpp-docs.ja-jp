---
title: "concurrent_unordered_multimap クラス | Microsoft Docs"
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
  - "concurrent_unordered_map/concurrency::concurrent_unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_multimap クラス"
ms.assetid: 4dada5d7-15df-4382-b9c9-348e75b2f3c1
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_multimap クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_unordered_multimap` クラスは、`std::pair<const _Key_type, _Element_type>` 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。  このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。  
  
## 構文  
  
```  
template <  
   typename _Key_type,  
   typename _Element_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<std::pair<const _Key_type,  
   _Element_type> >  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_multimap : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits<_Key_type, _Element_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, true> >;  
```  
  
#### パラメーター  
 `_Key_type`  
 キーの型。  
  
 `_Element_type`  
 マップされた型。  
  
 `_Hasher`  
 ハッシュ関数のオブジェクト型。  このオプションを省略すると、既定値は `std::tr1::hash<``_Key_type``>` になります。  
  
 `_Key_equality`  
 等価比較関数のオブジェクト型。  このオプションを省略すると、既定値は `std::equal_to<``_Key_type``>` になります。  
  
 `_Allocator_type`  
 同時実行ベクターのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  このオプションを省略すると、既定値は `std::allocator<std::pair<``_Key_type`, `_Element_type``>>` になります。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`allocator_type`|ストレージを管理するためのアロケーターの型です。|  
|`const_iterator`|被制御シーケンスの定数反復子の型です。|  
|`const_local_iterator`|被制御シーケンスの定数バケット反復子の型です。|  
|`const_pointer`|要素への定数ポインターの型です。|  
|`const_reference`|要素への定数参照の型です。|  
|`difference_type`|2 つの要素間の距離を表す、符号付きの型です。|  
|`hasher`|ハッシュ関数の型です。|  
|`iterator`|被制御シーケンスの反復子の型です。|  
|`key_equal`|比較関数の型です。|  
|`key_type`|順序付けキーの型です。|  
|`local_iterator`|被制御シーケンスのバケット反復子の型です。|  
|`mapped_type`|各キーに関連付けられた、マップされた値の型です。|  
|`pointer`|要素へのポインターの型です。|  
|`reference`|要素への参照の型です。|  
|`size_type`|2 つの要素間の距離を表す、符号なしの型です。|  
|`value_type`|要素の型。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_multimap::concurrent\_unordered\_multimap コンストラクター](../Topic/concurrent_unordered_multimap::concurrent_unordered_multimap%20Constructor.md)|オーバーロードされます。  同時実行順序なしのマルチマップを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_multimap::hash\_function メソッド](../Topic/concurrent_unordered_multimap::hash_function%20Method.md)|格納されているハッシュ関数オブジェクトを返します。|  
|[concurrent\_unordered\_multimap::insert メソッド](../Topic/concurrent_unordered_multimap::insert%20Method.md)|オーバーロードされます。  要素を `concurrent_unordered_multimap` オブジェクトに追加します。|  
|[concurrent\_unordered\_multimap::key\_eq メソッド](../Topic/concurrent_unordered_multimap::key_eq%20Method.md)|格納された等価比較関数のオブジェクトを返します。|  
|[concurrent\_unordered\_multimap::swap メソッド](../Topic/concurrent_unordered_multimap::swap%20Method.md)|2 つの `concurrent_unordered_multimap` オブジェクトのコンテンツを交換します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_unordered\_multimap::unsafe\_erase メソッド](../Topic/concurrent_unordered_multimap::unsafe_erase%20Method.md)|オーバーロードされます。  `concurrent_unordered_multimap` から指定した位置にある要素を削除します。  このメソッドは同時実行セーフではありません。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_multimap::operator\= 演算子](../Topic/concurrent_unordered_multimap::operator=%20Operator.md)|オーバーロードされます。  別の `concurrent_unordered_multimap` オブジェクトの内容をこのオブジェクトに割り当てます。  このメソッドは同時実行セーフではありません。|  
  
## 解説  
 `concurrent_unordered_multimap` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multimap`  
  
## 必要条件  
 **ヘッダー:** concurrent\_unordered\_map.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)