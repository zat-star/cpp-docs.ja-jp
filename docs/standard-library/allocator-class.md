---
title: "allocator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::allocator"
  - "allocator"
  - "memory/std::allocator"
  - "std.allocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator クラス"
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# allocator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、**Type** 型のオブジェクトの配列に対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。**allocator** クラスのオブジェクトは、標準 C\+\+ ライブラリのいくつかのコンテナー テンプレート クラスのコンストラクターで指定されている既定のアロケーター オブジェクトです。  
  
## 構文  
  
```  
  
template <class   
Type  
>  
class allocator  
  
```  
  
#### パラメーター  
 *型*  
 ストレージが割り当てまたは割り当て解除されるオブジェクトの型。  
  
## 解説  
 すべての標準テンプレート ライブラリのコンテナーには、**allocator** を既定値として持つテンプレート パラメーターがあります。 カスタム アロケーターを持つコンテナーを作成すると、そのコンテナーの要素の割り当てと解放を制御できます。  
  
 たとえば、アロケーター オブジェクトは、プライベート ヒープまたは共有メモリ内でストレージを割り当てたり、小さなまたは大きなオブジェクトのサイズ用に最適化したりできます。 さらに、種類の型定義を介して、共有メモリを管理する特殊なアクセサー オブジェクトを経由で要素にアクセスすること、または自動ガベージ コレクションを実行することを指定できます。 そのため、アロケーター オブジェクトを使用してストレージを割り当てるクラスでは、標準 C\+\+ ライブラリのコンテナーと同様に、これらの型を使用してポインターおよび参照オブジェクトを宣言する必要があります。  
  
 **\(C\_\+\+98\/03 のみ\)** allocator クラスから派生するときは、`_Other` typedef で新しく派生するクラスを参照する [rebind](../Topic/allocator::rebind.md) 構造体を指定する必要があります。  
  
 したがって、アロケーターは、次の型を定義します。  
  
-   [pointer](../Topic/allocator::pointer.md) は、**Type** へのポインターのように動作します。  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md) は、**Type** への const ポインターのように動作します。  
  
-   [reference](../Topic/allocator::reference.md) は、**Type** の参照のように動作します。  
  
-   [const\_reference](../Topic/allocator::const_reference.md) は、**Type** の定数参照のように動作します。  
  
 これらの **Type** は、割り当てられる要素に対してポインターと参照が従う必要がある形式を指定します  \(**allocator** クラスの明確な定義があるにもかかわらず、[allocator::pointer](../Topic/allocator::pointer.md) は、必ずしもすべてのアロケーター オブジェクトで **Type**\* と同じではありません\)。  
  
 **C\+\+ 11 以降:** アロケーターでの移動操作を有効にするには、最小限のアロケーター インターフェイスを使用し、さらにコピー コンストラクター、\=\= 演算子、\! \= 演算子、allocate、および deallocate を実装します。 詳細および例については、「[アロケーター](../Topic/Allocators.md)」を参照してください。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[allocator](../Topic/allocator::allocator.md)|`allocator` オブジェクトを作成するために使用するコンストラクター。|  
  
### Typedefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator::const_pointer.md)|アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。|  
|[const\_reference](../Topic/allocator::const_reference.md)|アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。|  
|[difference\_type](../Topic/allocator::difference_type.md)|アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。|  
|[pointer](../Topic/allocator::pointer.md)|アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。|  
|[参照](../Topic/allocator::reference.md)|アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。|  
|[size\_type](../Topic/allocator::size_type.md)|テンプレート クラス `allocator` のオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。|  
|[value\_type](../Topic/allocator::value_type.md)|アロケーターによって管理される型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[アドレス](../Topic/allocator::address.md)|値が指定されたオブジェクトのアドレスを検索します。|  
|[allocate](../Topic/allocator::allocate.md)|指定された要素数だけは格納できるメモリのブロックを割り当てます。|  
|[construct](../Topic/allocator::construct.md)|指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。|  
|[deallocate](../Topic/allocator::deallocate.md)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[destroy](../Topic/allocator::destroy.md)|オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。|  
|[max\_size](../Topic/allocator::max_size.md)|空きメモリがすべて使用される前に `allocator` クラスによって割り当てることのできる、型 `Type` の要素の数を返します。|  
|[rebind](../Topic/allocator::rebind.md)|1 つの型のオブジェクトのアロケーターを使用して別の型のオブジェクトのストレージの割り当てを可能にする構造体。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\=](../Topic/allocator::operator=.md)|`allocator` オブジェクトを別の `allocator` オブジェクトに割り当てます。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)