---
title: "allocator_traits クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- memory/std::allocator_traits
- memory/std::allocator_traits::propagate_on_container_move_assignment
- memory/std::allocator_traits::const_pointer
- memory/std::allocator_traits::propagate_on_container_swap
- memory/std::allocator_traits::propagate_on_container_copy_assignment
- memory/std::allocator_traits::difference_type
- memory/std::allocator_traits::allocator_type
- memory/std::allocator_traits::value_type
- memory/std::allocator_traits::pointer
- memory/std::allocator_traits::size_type
- memory/std::allocator_traits::const_void_pointer
- memory/std::allocator_traits::void_pointer
- memory/std::allocator_traits::allocate
- memory/std::allocator_traits::construct
- memory/std::allocator_traits::deallocate
- memory/std::allocator_traits::destroy
- memory/std::allocator_traits::max_size
- memory/std::allocator_traits::select_on_container_copy_construction
dev_langs:
- C++
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::allocator_traits [C++]
- std::allocator_traits [C++], propagate_on_container_move_assignment
- std::allocator_traits [C++], const_pointer
- std::allocator_traits [C++], propagate_on_container_swap
- std::allocator_traits [C++], propagate_on_container_copy_assignment
- std::allocator_traits [C++], difference_type
- std::allocator_traits [C++], allocator_type
- std::allocator_traits [C++], value_type
- std::allocator_traits [C++], pointer
- std::allocator_traits [C++], size_type
- std::allocator_traits [C++], const_void_pointer
- std::allocator_traits [C++], void_pointer
- std::allocator_traits [C++], allocate
- std::allocator_traits [C++], construct
- std::allocator_traits [C++], deallocate
- std::allocator_traits [C++], destroy
- std::allocator_traits [C++], max_size
- std::allocator_traits [C++], select_on_container_copy_construction
ms.workload:
- cplusplus
ms.openlocfilehash: d732b91a1c7a288cf22fea61e9565a794bb3380d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="allocatortraits-class"></a>allocator_traits クラス
このテンプレート クラスは、*allocator type* を補足するオブジェクトを記述します。 アロケーターの型は、割り当てられた記憶域を管理するために使用されるアロケーター オブジェクトを記述する任意の型です。 具体的には、任意のアロケーターの型 `Alloc` に対し、`allocator_traits<Alloc>` を使用してアロケーター対応のコンテナーが必要とするすべての情報を決定することができます。 詳細については、既定の「[allocator クラス](../standard-library/allocator-class.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class Alloc>
class allocator_traits;
```  
  
### <a name="typedefs"></a>Typedefs  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_traits::allocator_type`|この型は、テンプレート パラメーター `Alloc` のシノニムです。|  
|`allocator_traits::const_pointer`|この型は、整形式の場合は `Alloc::const_pointer`、それ以外の場合は `pointer_traits<pointer>::rebind<const value_type>` です。|  
|`allocator_traits::const_void_pointer`|この型は、整形式の場合は `Alloc::const_void_pointer`、それ以外の場合は `pointer_traits<pointer>::rebind<const void>` です。|  
|`allocator_traits::difference_type`|この型は、整形式の場合は `Alloc::difference_type`、それ以外の場合は `pointer_traits<pointer>::difference_type` です。|  
|`allocator_traits::pointer`|この型は、整形式の場合は `Alloc::pointer`、それ以外の場合は `value_type *` です。|  
|`allocator_traits::propagate_on_container_copy_assignment`|この型は、整形式の場合は `Alloc::propagate_on_container_copy_assignment`、それ以外の場合は `false_type` です。|  
|`allocator_traits::propagate_on_container_move_assignment`|この型は、整形式の場合は `Alloc::propagate_on_container_move_assignment`、それ以外の場合は `false_type` です。 型が true を保持している場合、アロケーター対応のコンテナーは移動代入で格納されたアロケーターをコピーします。|  
|`allocator_traits::propagate_on_container_swap`|この型は、整形式の場合は `Alloc::propagate_on_container_swap`、それ以外の場合は `false_type` です。 型が true を保持している場合、アロケーター対応のコンテナーはスワップで格納されたアロケーターをスワップします。|  
|`allocator_traits::size_type`|この型は、整形式の場合は `Alloc::size_type`、それ以外の場合は `make_unsigned<difference_type>::type` です。|  
|`allocator_traits::value_type`|この型は `Alloc::value_type` のシノニムです。|  
|`allocator_traits::void_pointer`|この型は、整形式の場合は `Alloc::void_pointer`、それ以外の場合は `pointer_traits<pointer>::rebind<void>` です。|  
  
### <a name="static-methods"></a>静的メソッド  
 次の静的メソッドは、特定のアロケーター パラメーターで対応するメソッドを呼び出します。  
  
|name|説明|  
|----------|-----------------|  
|[allocate](#allocate)|特定のアロケーター パラメーターを使用してメモリを割り当てる静的メソッド。|  
|[construct](#construct)|オブジェクトの構築に指定されたアロケーターを使用する静的メソッド。|  
|[deallocate](#deallocate)|指定したアロケーターを使用して、指定数のオブジェクトの割り当てを解除する静的メソッド。|  
|[destroy](#destroy)|指定したアロケーターを使用して、メモリの割り当てを解除せず、オブジェクトでデストラクターを呼び出す静的メソッド。|  
|[max_size](#max_size)|指定したアロケーターを使用して割り当てることができるオブジェクトの最大数を決定する静的メソッド。|  
|[select_on_container_copy_construction](#select_on_container_copy_construction)|指定したアロケーターで `select_on_container_copy_construction` を呼び出す静的メソッド。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
##  <a name="allocate"></a>  allocator_traits::allocate
 特定のアロケーター パラメーターを使用してメモリを割り当てる静的メソッド。  
  
```cpp  
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
 `count`  
 割り当てる要素数。  
  
 `hint`  
 記憶域への要求を、要求の前に割り当てられたオブジェクトのアドレスを見つけることで満たすことについて、アロケーター オブジェクトを支援できる `const_pointer`。 Null ポインターは、hint なしとして扱われます。  
  
### <a name="return-value"></a>戻り値  
 各メソッドは、割り当てられたオブジェクトへのポインターを返します。  
  
 最初の静的メソッドは `al.allocate(count)` を返します。  
  
 2 番目のメソッドは、その式が整形式の場合は `al.allocate(count, hint)` を返し、それ以外の場合は `al.allocate(count)` を返します。  
  
##  <a name="construct"></a>  allocator_traits::construct
 オブジェクトの構築に指定されたアロケーターを使用する静的メソッド。  
  
```cpp  
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
 `ptr`  
 オブジェクトが構築される場所へのポインター。  
  
 `args`  
 オブジェクト コンストラクターに渡される引数のリスト。  
  
### <a name="remarks"></a>コメント  
 静的メンバー関数は、その式が整形式の場合は `al.construct(ptr, args...)` を呼び出し、それ以外の場合は `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)` を評価します。  
  
##  <a name="deallocate"></a>  allocator_traits::deallocate
 指定したアロケーターを使用して、指定数のオブジェクトの割り当てを解除する静的メソッド。  
  
```cpp  
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
 `ptr`  
 割り当てを解除されるオブジェクトの開始位置へのポインター。  
  
 `count`  
 割り当てを解除するオブジェクトの数。  
  
### <a name="remarks"></a>コメント  
 このメソッドは `al.deallocate(ptr, count)` を呼び出します。  
  
 このメソッドは何もスローしません。  
  
##  <a name="destroy"></a>  allocator_traits::destroy
 指定したアロケーターを使用して、メモリの割り当てを解除せず、オブジェクトでデストラクターを呼び出す静的メソッド。  
  
```cpp  
template <class Uty>
static void destroy(Alloc& al, Uty* ptr);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
 `ptr`  
 オブジェクトの場所へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、その式が整形式の場合は `al.destroy(ptr)` を呼び出し、それ以外の場合は `ptr->~Uty()` を評価します。  
  
##  <a name="max_size"></a>  allocator_traits::max_size
 指定したアロケーターを使用して割り当てることができるオブジェクトの最大数を決定する静的メソッド。  
  
```cpp  
static size_type max_size(const Alloc& al);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、その式が整形式の場合は `al.max_size()` を返し、それ以外の場合は `numeric_limits<size_type>::max()` を返します。  
  
##  <a name="select_on_container_copy_construction"></a>  allocator_traits::select_on_container_copy_construction
 指定したアロケーターで `select_on_container_copy_construction` を呼び出す静的メソッド。  
  
```cpp  
static Alloc select_on_container_copy_construction(const Alloc& al);
```  
  
### <a name="parameters"></a>パラメーター  
 `al`  
 アロケーター オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、その型が整形式の場合は `al.select_on_container_copy_construction()` を返し、それ以外の場合は `al` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、関連するコンテナーがコピー構築された場合に、アロケーターを指定するために使用されます。  
  
## <a name="see-also"></a>参照  
 [\<memory>](../standard-library/memory.md)   
 [pointer_traits 構造体](../standard-library/pointer-traits-struct.md)   
 [scoped_allocator_adaptor クラス](../standard-library/scoped-allocator-adaptor-class.md)
