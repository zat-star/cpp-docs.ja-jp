---
title: "concurrent_unordered_set クラス | Microsoft Docs"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_set クラス"
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# concurrent_unordered_set クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_unordered_set` クラスは、\_Key\_type 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。  このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。  
  
## 構文  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_set : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### パラメーター  
 `_Key_type`  
 キーの型。  
  
 `_Hasher`  
 ハッシュ関数のオブジェクト型。  このオプションを省略すると、既定値は `std::tr1::hash<``_Key_type``>` になります。  
  
 `_Key_equality`  
 等価比較関数のオブジェクト型。  このオプションを省略すると、既定値は `std::equal_to<``_Key_type``>` になります。  
  
 `_Allocator_type`  
 同時実行順序なしのセットのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  このオプションを省略すると、既定値は `std::allocator<``_Key_type``>` になります。  
  
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
|`pointer`|要素へのポインターの型です。|  
|`reference`|要素への参照の型です。|  
|`size_type`|2 つの要素間の距離を表す、符号なしの型です。|  
|`value_type`|要素の型。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_set::concurrent\_unordered\_set コンストラクター](../Topic/concurrent_unordered_set::concurrent_unordered_set%20Constructor.md)|オーバーロードされます。  同時実行順序なしのセットを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_set::hash\_function メソッド](../Topic/concurrent_unordered_set::hash_function%20Method.md)|格納されているハッシュ関数オブジェクトを返します。|  
|[concurrent\_unordered\_set::insert メソッド](../Topic/concurrent_unordered_set::insert%20Method.md)|オーバーロードされます。  要素を `concurrent_unordered_set` オブジェクトに追加します。|  
|[concurrent\_unordered\_set::key\_eq メソッド](../Topic/concurrent_unordered_set::key_eq%20Method.md)|格納された等価比較関数のオブジェクトを返します。|  
|[concurrent\_unordered\_set::swap メソッド](../Topic/concurrent_unordered_set::swap%20Method.md)|2 つの `concurrent_unordered_set` オブジェクトのコンテンツを交換します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_unordered\_set::unsafe\_erase メソッド](../Topic/concurrent_unordered_set::unsafe_erase%20Method.md)|オーバーロードされます。  `concurrent_unordered_set` から指定した位置にある要素を削除します。  このメソッドは同時実行セーフではありません。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_unordered\_set::operator\= 演算子](../Topic/concurrent_unordered_set::operator=%20Operator.md)|オーバーロードされます。  別の `concurrent_unordered_set` オブジェクトの内容をこのオブジェクトに割り当てます。  このメソッドは同時実行セーフではありません。|  
  
## 解説  
 `concurrent_unordered_set` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## 必要条件  
 **ヘッダー:** concurrent\_unordered\_set.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)