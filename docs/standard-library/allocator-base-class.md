---
title: "allocator_base クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators.allocator_base"
  - "stdext.allocators.allocator_base"
  - "allocator_base"
  - "allocators/stdext::allocator_base"
  - "stdext::allocator_base"
  - "stdext::allocators::allocator_base"
  - "allocators/stdext::allocators::allocator_base"
  - "allocators::allocator_base"
  - "stdext.allocator_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_base クラス"
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# allocator_base クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

同期フィルターからユーザー定義のアロケーターを作成するために必要な、基底クラスと共通の関数を定義します。  
  
## 構文  
  
```  
template <class Type, class Sync> class allocator_base  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
|`Sync`|アロケーターの同期ポリシー。[sync\_none クラス](../standard-library/sync-none-class.md)、[sync\_per\_container クラス](../standard-library/sync-per-container-class.md)、[sync\_per\_thread クラス](../standard-library/sync-per-thread-class.md)、[sync\_shared クラス](../Topic/sync_shared%20Class.md) のいずれかです。|  
  
### コンストラクター  
  
|||  
|-|-|  
|[allocator\_base](../Topic/allocator_base::allocator_base.md)|`allocator_base` 型のオブジェクトを構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator_base::const_pointer.md)|アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。|  
|[const\_reference](../Topic/allocator_base::const_reference.md)|アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。|  
|[difference\_type](../Topic/allocator_base::difference_type.md)|アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。|  
|[ポインター](../Topic/allocator_base::pointer.md)|アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。|  
|[参照](../Topic/allocator_base::reference.md)|アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。|  
|[size\_type](../Topic/allocator_base::size_type.md)|テンプレート クラス `allocator_base` のオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。|  
|[value\_type](../Topic/allocator_base::value_type.md)|アロケーターによって管理される型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[\_Charalloc](../Topic/allocator_base::_Charalloc.md)|型 `char` の配列のストレージを割り当てます。|  
|[\_Chardealloc](../Topic/allocator_base::_Chardealloc.md)|型 `char` の要素を含む配列のストレージを解放します。|  
|[アドレス](../Topic/allocator_base::address.md)|値が指定されたオブジェクトのアドレスを検索します。|  
|[allocate](../Topic/allocator_base::allocate.md)|指定された要素数だけは格納できるメモリのブロックを割り当てます。|  
|[construct](../Topic/allocator_base::construct.md)|指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。|  
|[deallocate](../Topic/allocator_base::deallocate.md)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[destroy](../Topic/allocator_base::destroy.md)|オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。|  
|[max\_size](../Topic/allocator_base::max_size.md)|空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、型 `Type` の要素の数を返します。|  
  
## 必要条件  
 **ヘッダー:** \<allocators\>  
  
 **名前空間:** stdext  
  
## 参照  
 [\<allocators\>](../standard-library/allocators-header.md)