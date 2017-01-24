---
title: "unique_ptr クラス | Microsoft Docs"
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
  - "unique_ptr"
  - "std.unique_ptr"
  - "std::unique_ptr"
  - "memory/std::unique_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_ptr クラス"
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unique_ptr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

所有されているオブジェクトまたは配列へのポインターを格納します。  このオブジェクトと配列は、この `unique_ptr` によってのみ所有されます。  このオブジェクトと配列は、`unique_ptr` が破棄されたときに破棄されます。  
  
## 構文  
  
```  
template< class T, class Del = default_delete<T> >  
    class unique_ptr {  
public:  
    unique_ptr( );  
    unique_ptr( nullptr_t Nptr );  
    explicit unique_ptr( pointer Ptr );  
    unique_ptr( pointer Ptr,  
        typename conditional<is_reference<Del>::value,   
            Del,  
            typename add_reference<const Del>::type>::type Deleter);  
    unique_ptr (pointer Ptr,  
        typename remove_reference<Del>::type&& Deleter);  
    unique_ptr (unique_ptr&& Right);  
    template<class T2, Class Del2> unique_ptr( unique_ptr<T2, Del2>&& Right );  
    unique_ptr( const unique_ptr& Right    ) = delete;  
    unique_ptr& operator=(const unique_ptr& Right     ) = delete;  
};  
  
```  
  
```  
//Specialization for arrays:  
template <class T, class D> class unique_ptr<T[], D>   
{   public:       
     typedef pointer;  
     typedef T element_type;  
     typedef D deleter_type;  
  
     constexpr unique_ptr() noexcept;  
     template <class U> explicit unique_ptr(U p) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     unique_ptr(unique_ptr&& u) noexcept;  
     constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }  
     template <class U, class E>  
       unique_ptr(unique_ptr<U, E>&& u) noexcept;  
  
     ~unique_ptr();  
  
     unique_ptr& operator=(unique_ptr&& u) noexcept;  
     template <class U, class E>  
       unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;  
     unique_ptr& operator=(nullptr_t) noexcept;  
  
     T& operator[](size_t i) const;  
     pointer get() const noexcept;  
     deleter_type& get_deleter() noexcept;  
     const deleter_type& get_deleter() const noexcept;  
     explicit operator bool() const noexcept;  
  
     pointer release() noexcept;  
     void reset(pointer p = pointer()) noexcept;  
     void reset(nullptr_t = nullptr) noexcept;  
     template <class U> void reset(U p) noexcept = delete;  
     void swap(unique_ptr& u) noexcept;  
  
    // disable copy from lvalue  
     unique_ptr(const unique_ptr&) = delete;  
     unique_ptr& operator=(const unique_ptr&) = delete;  
   };  
 }  
  
```  
  
#### パラメーター  
 `Right`  
 `unique_ptr`  
  
 `Nptr`  
 `rvalue` 型の `std::nullptr_t`。  
  
 `Ptr`  
 `pointer`  
  
 `Deleter`  
 `deleter` にバインドされている `unique_ptr` 関数。  
  
## 例外  
 例外は `unique_ptr` で生成されません。  
  
## 解説  
 `unique_ptr` クラスは、`auto_ptr` に代わるものであり、STL コンテナーの要素として使用できます。  
  
 効率的に [make\_unique](../Topic/make_unique.md) の新しいインスタンスを作成するには、`unique_ptr` ヘルパー関数を使用します。  
  
 `unique_ptr` は一意にリソースを管理します。  `unique_ptr` オブジェクトは null ポインターを所有または保存するオブジェクトへのポインターを格納します。  リソースを所有できるのは、1 つの `unique_ptr` オブジェクトのみです。  特定のリソースを所有する `unique_ptr` オブジェクトが破棄された時点で、リソースが解放されます。  `unique_ptr` オブジェクトは移動できますが、コピーできません。  詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
 特定の `deleter` に対するリソースの割り当てを認識する、`Del` 型の格納された `unique_ptr` オブジェクトを呼び出すことによって、リソースが解放されます。  既定の `deleter` `default_delete``<T>` は、`_Ptr` が指すリソースが、`new` に割り当てられることと、`delete _``Ptr` を呼び出すことによって解放できることを前提としています   \(部分的特殊化 `unique_ptr<T[]>` は `new[]` で割り当てられた配列オブジェクトを管理します。また、delete\[\] `deleter` の呼び出しに特化した既定の `default_delete<T[]>` `_Ptr` があります\)。  
  
 所有されたリソースに対する格納されたポインター、`stored_ptr` には、`pointer` 型があります。  これは、定義されている場合は `Del::pointer`、定義されていない場合は `T *`  です。  `deleter` がステートレスである場合、格納された `stored_deleter` オブジェクトである `deleter` はオブジェクト内の領域を使用しません。  `Del` が参照型である場合があることに注意してください。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[unique\_ptr::unique\_ptr](../Topic/unique_ptr::unique_ptr.md)|`unique_ptr` には、7 種類のコンストラクターがあります。|  
  
### Typedefs  
  
|||  
|-|-|  
|[deleter\_type](../Topic/deleter_type.md)|テンプレート パラメーター `Del` のシノニム。|  
|[element\_type](../Topic/element_type.md)|テンプレート パラメーター `T``.` のシノニム。|  
|[ポインター](../Topic/pointer.md)|定義されている場合は `Del::pointer` のシノニム、それ以外の場合は `T *` のシノニム。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[unique\_ptr::get](../Topic/unique_ptr::get.md)|`stored_ptr` を返します。|  
|[unique\_ptr::get\_deleter](../Topic/unique_ptr::get_deleter.md)|`stored_deleter` への参照を返します。|  
|[unique\_ptr::release](../Topic/unique_ptr::release.md)|`pointer()` を `stored_ptr` に格納し、以前の内容を返します。|  
|[unique\_ptr::reset](../Topic/unique_ptr::reset.md)|現在所有されているリソースを解放し、新しいリソースを受け取ります。|  
|[unique\_ptr::swap](../Topic/unique_ptr::swap.md)|指定された `deleter` を使用して、リソースと `unique_ptr` を交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|`operator bool`|この演算子は、`bool` に変換可能な型の値を返します。  `bool` への変換結果は、`true` の場合は `get() != pointer()`、それ以外の場合は `false` です。|  
|`operator->`|このメンバー関数は、`stored_ptr``.` を返します。|  
|`operator*`|このメンバー関数は、\*`stored_ptr``.` を返します。|  
|[unique\_ptr operator\=](../Topic/unique_ptr%20operator=.md)|現在の `unique_ptr`  に `pointer-type` \(または `unique_ptr`\) の値を割り当てます。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [\<memory\>](../standard-library/memory.md)