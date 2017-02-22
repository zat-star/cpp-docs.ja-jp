---
title: "scoped_allocator_adaptor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.scoped_allocator_adaptor"
  - "scoped_allocator_adaptor"
  - "scoped_allocator/std::scoped_allocator_adaptor"
  - "std::scoped_allocator_adaptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scoped_allocator_adaptor クラス"
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# scoped_allocator_adaptor クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アロケーターの入れ子を表します。  
  
## 構文  
  
```cpp  
template<class Outer, class... Inner>  
    class scoped_allocator_adaptor;  
```  
  
## 解説  
 このテンプレート クラスは、一つ以上の入れ子をカプセル化します。  そのような各クラスに `outer_allocator_type`型の `scoped_allocator_adaptor` オブジェクトのパブリックなベースである `Outer`のシノニムの一番外側のアロケーターがあります。  `Outer` が コンテナーで使用されるメモリを割り当てるために使用されます。  `outer_allocator`を呼び出してこのアロケーター ベースのオブジェクトへの参照を取得できます。  
  
 入れ子の残りの部分を `inner_allocator_type`型があります。  内部のアロケーターがコンテナー内の要素のためにメモリを割り当てるために使用されます。  `inner_allocator`を呼び出すと、この型に格納されたオブジェクトへの参照を取得できます。  `Inner...` が空でない場合、`inner_allocator_type` に型 `scoped_allocator_adaptor<Inner...>`があり、`inner_allocator` はメンバー オブジェクトを指定します。  それ以外の場合は `inner_allocator_type` に型 `scoped_allocator_adaptor<Outer>`があり、`inner_allocator` は外部オブジェクトを指定します。  
  
 入れ子は任意の深さが同様に動作し、最も内側のカプセル化されたアロケーターを必要に応じてレプリケートします。  
  
 このテンプレート クラスの動作の説明の可視インターフェイス サポートの一部ではない複数の概念。  *外側のアロケーターは*、構造体および破棄のメソッドのすべての呼び出しを仲介します。  これは `OUTERMOST(X)` が次のいずれかの再帰関数 `OUTERMOST(X)`で効果的に定義されます。  
  
-   `X.outer_allocator()` が正しく構成されている場合 `OUTERMOST(X)` は `OUTERMOST(X.outer_allocator())`です。  
  
-   それ以外の場合、`OUTERMOST(X)` は `X` になります。  
  
 3 種類のは博覧 Workshop に定義されます。:  
  
|型|説明|  
|-------|--------|  
|`Outermost`|`OUTERMOST(*this)` の型。|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[scoped\_allocator\_adaptor::scoped\_allocator\_adaptor コンストラクター](../Topic/scoped_allocator_adaptor::scoped_allocator_adaptor%20Constructor.md)|`scoped_allocator_adaptor` オブジェクトを構築します。|  
  
### Typedef  
  
|名前|説明|  
|--------|--------|  
|`const_pointer`|この型は、アロケーター `Outer`に関連付けられている `const_pointer` のシノニムです。|  
|`const_void_pointer`|この型は、アロケーター `Outer`に関連付けられている `const_void_pointer` のシノニムです。|  
|`difference_type`|この型は、アロケーター `Outer`に関連付けられている `difference_type` のシノニムです。|  
|`inner_allocator_type`|この型は、入れ子になったアダプター `scoped_allocator_adaptor<Inner...>`の型のシノニムです。|  
|`outer_allocator_type`|この型は、基本 `Outer`アロケーターの型のシノニムです。|  
|`pointer`|この型は、アロケーター `Outer`に関連付けられている `pointer` のシノニムです。|  
|`propagate_on_container_copy_assignment`|型は `Outer_traits::propagate_on_container_copy_assignment` が当てはまるか、`inner_allocator_type::propagate_on_container_copy_assignment` が当てはまれば場合にも当てはまります。|  
|`propagate_on_container_move_assignment`|型は `Outer_traits::propagate_on_container_move_assignment` が当てはまるか、`inner_allocator_type::propagate_on_container_move_assignment` が当てはまれば場合にも当てはまります。|  
|`propagate_on_container_swap`|型は `Outer_traits::propagate_on_container_swap` が当てはまるか、`inner_allocator_type::propagate_on_container_swap` が当てはまれば場合にも当てはまります。|  
|`size_type`|この型は、アロケーター `Outer`に関連付けられている `size_type` のシノニムです。|  
|`value_type`|この型は、アロケーター `Outer`に関連付けられている `value_type` のシノニムです。|  
|`void_pointer`|この型は、アロケーター `Outer`に関連付けられている `void_pointer` のシノニムです。|  
  
### 構造体  
  
|名前|説明|  
|--------|--------|  
|[scoped\_allocator\_adaptor::rebind 構造体](../Topic/scoped_allocator_adaptor::rebind%20Struct.md)|`scoped_allocator_adaptor<Other, Inner...>`のシノニムと `Outer::rebind<Other>::other` 型を定義します。|  
  
### メソッド  
  
|名前|説明|  
|--------|--------|  
|[scoped\_allocator\_adaptor::allocate メソッド](../Topic/scoped_allocator_adaptor::allocate%20Method.md)|`Outer` のアロケーターを使用してメモリを割り当てます。|  
|[scoped\_allocator\_adaptor::construct Method](../Topic/scoped_allocator_adaptor::construct%20Method.md)|オブジェクトを構築します。|  
|[scoped\_allocator\_adaptor::deallocate メソッド](../Topic/scoped_allocator_adaptor::deallocate%20Method.md)|外部のアロケーターを使用してオブジェクトを解放します。|  
|[scoped\_allocator\_adaptor::destroy メソッド](../Topic/scoped_allocator_adaptor::destroy%20Method.md)|指定したオブジェクトを破棄します。|  
|[scoped\_allocator\_adaptor::inner\_allocator メソッド](../Topic/scoped_allocator_adaptor::inner_allocator%20Method.md)|型 `inner_allocator_type`に保存されたオブジェクトへの参照を取得します。|  
|[scoped\_allocator\_adaptor::max\_size メソッド](../Topic/scoped_allocator_adaptor::max_size%20Method.md)|外部のアロケーターに割り当てることができるオブジェクトの最大数を指定します。|  
|[scoped\_allocator\_adaptor::outer\_allocator メソッド](../Topic/scoped_allocator_adaptor::outer_allocator%20Method.md)|型 `outer_allocator_type`に保存されたオブジェクトへの参照を取得します。|  
|[scoped\_allocator\_adaptor::select\_on\_container\_copy\_construction メソッド](../Topic/scoped_allocator_adaptor::select_on_container_copy_construction%20Method.md)|対応するアロケーターの `select_on_container_copy_construction` を呼び出して初期化される各、格納されているアロケーター オブジェクトと `scoped_allocator_adaptor` の新しいオブジェクトを作成します。|  
  
## 必要条件  
 **ヘッダー:** の \<scoped\_allocator\>  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)