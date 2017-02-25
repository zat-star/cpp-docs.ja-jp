---
title: "concurrent_vector クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_vector/Concurrency::concurrent_vector"
  - "concurrent_vector/concurrency::concurrent_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_vector クラス"
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# concurrent_vector クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_vector` クラスは、任意の要素にランダムにアクセスできるようにするシーケンス コンテナー クラスです。  これを使用すると、同時実行セーフな追加、要素アクセス、反復子アクセス、および反復子走査の各操作を実行できます。  
  
## 構文  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_vector: protected details::_Allocator_base<_Ty, _Ax>, private details::_Concurrent_vector_base_v4;  
```  
  
#### パラメーター  
 `_Ty`  
 ベクターに格納される要素のデータ型。  
  
 `_Ax`  
 同時実行ベクターのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  このオプションを省略すると、既定値は `allocator<``_Ty``>` になります。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`allocator_type`|同時実行ベクターのアロケーター クラスを表す型。|  
|`const_iterator`|同時実行ベクター内の `const` 要素を読み取ることができるランダム アクセス反復子を提供する型。|  
|`const_pointer`|同時実行ベクター内の `const` 要素へのポインターを提供する型。|  
|`const_reference`|同時実行ベクターに格納されている `const` 要素の読み取りと操作実行のために、`const` 要素への参照を提供する型。|  
|`const_reverse_iterator`|同時実行ベクター内の任意の `const` 要素を読み取ることができるランダム アクセス反復子を提供する型。|  
|`difference_type`|同時実行ベクター内の 2 つの要素間の符号付き距離を提供する型。|  
|`iterator`|同時実行ベクター内の任意の要素を読み取ることができるランダム アクセス反復子を提供する型。  反復子を使用する要素の変更は同時実行セーフではありません。|  
|`pointer`|同時実行ベクター内の要素へのポインターを提供する型。|  
|`reference`|同時実行ベクターに格納されている要素への参照を提供する型。|  
|`reverse_iterator`|逆順の同時実行ベクター内の任意の要素を読み取ることができるランダム アクセス反復子を提供する型。  反復子を使用する要素の変更は同時実行セーフではありません。|  
|`size_type`|同時実行ベクター内の要素数をカウントする型。|  
|`value_type`|同時実行ベクターに格納されているデータ型を表す型。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_vector::concurrent\_vector コンストラクター](../Topic/concurrent_vector::concurrent_vector%20Constructor.md)|オーバーロードされます。  同時実行ベクターを構築します。|  
|[concurrent\_vector::~concurrent\_vector デストラクター](../Topic/concurrent_vector::~concurrent_vector%20Destructor.md)|すべての要素を消去し、この同時実行ベクターを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_vector::assign メソッド](../Topic/concurrent_vector::assign%20Method.md)|オーバーロードされます。  同時実行ベクターの要素を消去し、`_N` 個の `_Item` のコピー、または反復子範囲 \[`_Begin`, `_End`\) で指定された値を同時実行ベクターに割り当てます。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_vector::at メソッド](../Topic/concurrent_vector::at%20Method.md)|オーバーロードされます。  同時実行ベクター内の指定されたインデックス位置にある要素へのアクセスを提供します。  このメソッドは、読み取り操作に対して同時実行セーフです。また、`_Index` 値が同時実行ベクターのサイズを下回る限りは、ベクターの拡大時にも同時実行セーフです。|  
|[concurrent\_vector::back メソッド](../Topic/concurrent_vector::back%20Method.md)|オーバーロードされます。  同時実行ベクター内の最後の要素への参照または `const` 参照を返します。  同時実行ベクターが空の場合、戻り値は未定義です。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::begin メソッド](../Topic/concurrent_vector::begin%20Method.md)|オーバーロードされます。  同時実行ベクターの先頭を指す `iterator` 型または `const_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::capacity メソッド](../Topic/concurrent_vector::capacity%20Method.md)|メモリを追加割り当てせずに同時実行ベクターのサイズを拡張できる最大サイズを返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::cbegin メソッド](../Topic/concurrent_vector::cbegin%20Method.md)|同時実行ベクターの先頭を指す `const_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::cend メソッド](../Topic/concurrent_vector::cend%20Method.md)|同時実行ベクターの末尾を指す `const_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::clear メソッド](../Topic/concurrent_vector::clear%20Method.md)|同時実行ベクター内のすべての要素を消去します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_vector::crbegin メソッド](../Topic/concurrent_vector::crbegin%20Method.md)|同時実行ベクターの先頭を指す `const_reverse_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::crend メソッド](../Topic/concurrent_vector::crend%20Method.md)|同時実行ベクターの末尾を指す `const_reverse_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::empty メソッド](../Topic/concurrent_vector::empty%20Method.md)|このメソッドが呼び出された時点で同時実行ベクターが空であったかどうかをテストします。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::rend メソッド](../Topic/concurrent_vector::end%20Method.md)|オーバーロードされます。  同時実行ベクターの末尾を指す `iterator` 型または `const_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::front メソッド](../Topic/concurrent_vector::front%20Method.md)|オーバーロードされます。  同時実行ベクター内の最初の要素への参照または `const` 参照を返します。  同時実行ベクターが空の場合、戻り値は未定義です。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::get\_allocator メソッド](../Topic/concurrent_vector::get_allocator%20Method.md)|同時実行ベクターの構築に使用されるアロケーターのコピーを返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::grow\_by メソッド](../Topic/concurrent_vector::grow_by%20Method.md)|オーバーロードされます。  この同時実行ベクターを、`_Delta` 個の要素だけ拡大します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::grow\_to\_at\_least メソッド](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|この同時実行ベクターを、少なくとも `_N` 個の要素を保持できるまで拡大します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::max\_size メソッド](../Topic/concurrent_vector::max_size%20Method.md)|同時実行ベクターが保持できる要素の最大数を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::push\_back メソッド](../Topic/concurrent_vector::push_back%20Method.md)|オーバーロードされます。  指定されたアイテムを同時実行ベクターの末尾に追加します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::rbegin メソッド](../Topic/concurrent_vector::rbegin%20Method.md)|オーバーロードされます。  同時実行ベクターの先頭を指す `reverse_iterator` 型または `const_reverse_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::rend メソッド](../Topic/concurrent_vector::rend%20Method.md)|オーバーロードされます。  同時実行ベクターの末尾を指す `reverse_iterator` 型または `const_reverse_iterator` 型の反復子を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::reserve メソッド](../Topic/concurrent_vector::reserve%20Method.md)|後でメモリを追加割り当てする必要がないように、同時実行ベクターのサイズを `_N` まで拡大できるだけの領域を割り当てます。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_vector::resize メソッド](../Topic/concurrent_vector::resize%20Method.md)|オーバーロードされます。  同時実行ベクターのサイズを要求されたサイズに変更し、必要に応じて要素を追加または削除します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_vector::shrink\_to\_fit メソッド](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|同時実行ベクターの内部表現を圧縮して、断片化を少なくし、メモリの使用を最適化します。  このメソッドは同時実行セーフではありません。|  
|[concurrent\_vector::size メソッド](../Topic/concurrent_vector::size%20Method.md)|同時実行ベクター内の要素数を返します。  このメソッドは同時実行セーフです。|  
|[concurrent\_vector::swap メソッド](../Topic/concurrent_vector::swap%20Method.md)|2 つの同時実行ベクターのコンテンツを交換します。  このメソッドは同時実行セーフではありません。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[concurrent\_vector::operatorOperator](../Topic/concurrent_vector::operatorOperator.md)|オーバーロードされます。  同時実行ベクター内の指定されたインデックス位置にある要素へのアクセスを提供します。  このメソッドは、読み取り操作に対して同時実行セーフです。また、`_Index` 値が同時実行ベクターのサイズよりも小さい値である限りは、ベクターの拡大時にも同時実行セーフです。|  
|[concurrent\_vector::operator\= 演算子](../Topic/concurrent_vector::operator=%20Operator.md)|オーバーロードされます。  別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。  このメソッドは同時実行セーフではありません。|  
  
## 解説  
 `concurrent_vector` クラスの詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。  
  
## 継承階層  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## 必要条件  
 **ヘッダー:** concurrent\_vector.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)