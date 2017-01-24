---
title: "pointer_traits 構造体 | Microsoft Docs"
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
  - "memory/std::pointer_traits::element_type"
  - "memory/std::pointer_traits::pointer"
  - "memory/std::pointer_traits"
  - "memory/std::pointer_traits::difference_type"
  - "memory/std::pointer_traits::rebind"
  - "xmemory0/std::pointer_traits::element_type"
  - "xmemory0/std::pointer_traits::pointer"
  - "xmemory0/std::pointer_traits"
  - "xmemory0/std::pointer_traits::difference_type"
  - "xmemory0/std::pointer_traits::rebind"
dev_langs: 
  - "C++"
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointer_traits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Ptr` テンプレート クラスのオブジェクトが、ポインター型 `allocator_traits` を持つアロケーターを記述するために必要とする情報を提供します。  
  
## 構文  
  
```cpp  
template<class Ptr>  
    struct pointer_traits;  
```  
  
## 解説  
 Ptr は型 `Ty *` または次のプロパティを持つクラスの生ポインターです。  
  
```  
template<class Ty, class... Rest>  
    struct Ptr  
    { // describes a pointer type usable by allocators  
    typedef Ptr pointer;  
    typedef T1 element_type; // optional  
    typedef T2 difference_type; // optional  
    template<class Other>  
        using rebind = typename Ptr<Other, Rest...>; // optional  
  
    static pointer pointer_to(element_type& obj); // optional  
    };  
```  
  
> [!WARNING]
>  C\+\+ 標準でエイリアスのテンプレートとして `rebind` のメンバーを指定すると、Visual C\+\+ には `struct`として再を実装します。  
  
### Typedef  
  
|名前|説明|  
|--------|--------|  
|`typedef T2 difference_type`|その型がある場合 `T2``Ptr::difference_type` 型は、それ `ptrdiff_t`です。  `Ptr` が生ポインターの場合、型は `ptrdiff_t`です。|  
|`typedef T1 element_type`|その型がある場合 `T1``Ptr::element_type` 型は、それ `Ty`です。  `Ptr` が生ポインターの場合、型は `Ty`です。|  
|`typedef Ptr pointer`|型は `Ptr` です。|  
  
### 構造体  
  
|名前|説明|  
|--------|--------|  
|`pointer_traits::rebind`|指定された型になるポインター型を変換します。|  
  
### メソッド  
  
|名前|説明|  
|--------|--------|  
|[pointer\_traits::pointer\_to メソッド](../Topic/pointer_traits::pointer_to%20Method.md)|クラス `Ptr`オブジェクトへの任意の参照を変換します。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [\<memory\>](../standard-library/memory.md)   
 [allocator\_traits クラス](../Topic/allocator_traits%20Class.md)