---
title: "concurrent_unordered_map クラス | Microsoft Docs"
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
  - "concurrent_unordered_map/concurrency::concurrent_unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_map クラス"
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_map クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_unordered_map` クラスは、`std::pair<const _Key_type, _Element_type>` 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。  このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。  
  
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
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_map : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits<_Key_type, _Element_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
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
 同時実行順序なしのマップのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  このオプションを省略すると、既定値は `std::allocator<std::pair<``_Key_type`, `_Element_type``>>` になります。  
  
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
|[concurrent\_unordered\_map::concurrent\_unordered\_map コンストラクター](../Topic/concurrent_unordered_map::concurrent_unordered_map%20Constructor.md)|オーバーロードされます。  同時実行順序なしのマップを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_map::at メソッド](../Topic/concurrent_unordered_map::at%20Method.md)|オーバーロードされます。  `concurrent_unordered_map` 内の指定されたキー値を持つ要素を検索します。  このメソッドは同時実行セーフです。|  
|[concurrent\_unordered\_map::hash\_function メソッド](../Topic/concurrent_unordered_map::hash_function%20Method.md)|格納されているハッシュ関数オブジェクトを取得します。|  
|[concurrent\_unordered\_map::insert メソッド](../Topic/concurrent_unordered_map::insert%20Method.md)|オーバーロードされます。  要素を `concurrent_unordered_map` オブジェクトに追加します。|  
|[concurrent\_unordered\_map::key\_eq メソッド](../Topic/concurrent_unordered_map::key_eq%20Method.md)|格納された等価比較関数のオブジェクトを取得します。|  
|[concurrent\_unordered\_map::swap メソッド](../Topic/concurrent_unordered_map::swap%20Method.md)|2 つの `concurrent_unordered_map` オブジェクトのコンテンツを交換します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_unordered\_map::unsafe\_erase メソッド](../Topic/concurrent_unordered_map::unsafe_erase%20Method.md)|オーバーロードされます。  `concurrent_unordered_map` から指定した位置にある要素を削除します。  このメソッドは同時実行セーフではありません。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_map::operatorOperator](../Topic/concurrent_unordered_map::operatorOperator.md)|オーバーロードされます。  指定したキーを持つ要素を検索または挿入します。  このメソッドは同時実行セーフです。|  
|[concurrent\_unordered\_map::operator\= 演算子](../Topic/concurrent_unordered_map::operator=%20Operator.md)|オーバーロードされます。  別の `concurrent_unordered_map` オブジェクトの内容をこのオブジェクトに割り当てます。  このメソッドは同時実行セーフではありません。|  
  
## 解説  
 `concurrent_unordered_map` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## 必要条件  
 **ヘッダー:** concurrent\_unordered\_map.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)