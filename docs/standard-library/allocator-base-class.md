---
title: "allocator_base クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocator_base
- allocators/stdext::allocator_base
- stdext::allocator_base
- stdext::allocators::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
dev_langs:
- C++
helpviewer_keywords:
- allocator_base class
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 11e6300d0d625f419e47d5f60f1db175419e3420
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="allocatorbase-class"></a>allocator_base クラス
同期フィルターからユーザー定義のアロケーターを作成するために必要な、基底クラスと共通の関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type, class Sync>  
class allocator_base
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
|`Sync`|アロケーターの同期ポリシー。[sync_none クラス](../standard-library/sync-none-class.md)、[sync_per_container クラス](../standard-library/sync-per-container-class.md)、[sync_per_thread クラス](../standard-library/sync-per-thread-class.md)、[sync_shared クラス](../standard-library/sync-shared-class.md)のいずれかです。|  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[allocator_base](#allocator_base)|`allocator_base` 型のオブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。|  
|[const_reference](#const_reference)|アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。|  
|[difference_type](#difference_type)|アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。|  
|[pointer](#pointer)|アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。|  
|[reference](#reference)|アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。|  
|[size_type](#size_type)|テンプレート クラス `allocator_base` のオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。|  
|[value_type](#value_type)|アロケーターによって管理される型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[_Charalloc](#charalloc)|型 `char` の配列のストレージを割り当てます。|  
|[_Chardealloc](#chardealloc)|型 `char` の要素を含む配列のストレージを解放します。|  
|[address](#address)|値が指定されたオブジェクトのアドレスを検索します。|  
|[allocate](#allocate)|指定された要素数だけは格納できるメモリのブロックを割り当てます。|  
|[construct](#construct)|指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[destroy](#destroy)|オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。|  
|[max_size](#max_size)|空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、型 `Type` の要素の数を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="charalloc"></a>  allocator_base::_Charalloc  
 型 `char` の配列のストレージを割り当てます。  
  
```
char *_Charalloc(size_type count);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`count`|割り当てられる配列内の要素の数。|  
  
### <a name="return-value"></a>戻り値  
 割り当てられたオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、再バインドをコンパイルできないコンパイラでコンパイルした場合に、コンテナーによって使用されます。 この関数は、同期フィルターの `allocate` 関数への呼び出しの結果を返すことで、ユーザー定義のアロケーターに `_Charalloc` を実装します。  
  
##  <a name="chardealloc"></a>  allocator_base::_Chardealloc  
 型 `char` の要素を含む配列のストレージを解放します。  
  
```
void _Chardealloc(void* ptr, size_type count);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|  
|`count`|記憶域から割り当てを解除されるオブジェクトの数。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、再バインドをコンパイルできないコンパイラでコンパイルした場合に、コンテナーによって使用されます。 この関数は、同期フィルターの `deallocate` 関数を呼び出すことで、ユーザー定義のアロケーターに `_Chardealloc` を実装します。 ポインター ptr は、同じサイズと型の配列オブジェクトを割り当てる `*this` と等しいことを比較するアロケーター オブジェクトに対し、`_Charalloc` を呼び出すことで、既に返されているはずです。 `_Chardealloc` は例外をスローしません。  
  
##  <a name="address"></a>  allocator_base::address  
 値が指定されたオブジェクトのアドレスを検索します。  
  
```
pointer address(reference val);

const_pointer address(const_reference val);
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 アドレスが検索対象となっているオブジェクトの const 値または nonconst 値。  
  
### <a name="return-value"></a>戻り値  
 見つかった const 値または nonconst 値のそれぞれのオブジェクトに対する const ポインターまたは nonconst ポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`&val` を返すことで、ユーザー定義のアロケーターに実装されます。  
  
##  <a name="allocate"></a>  allocator_base::allocate  
 指定された要素数だけは格納できるメモリのブロックを割り当てます。  
  
```
template <class Other>  
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|割り当てられる配列内の要素の数。|  
|`_Hint`|このパラメーターは無視されます。|  
  
### <a name="return-value"></a>戻り値  
 割り当てられたオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、`_Nx == 1` の場合、Type `*` 型の同期フィルターの `allocate` 関数への呼び出しの結果を返すことで、ユーザー定義のアロケーターにメモリ割り当てを実装します。それ以外の場合は、`operator new(_Nx * sizeof(Type))` への呼び出しの結果を返すことで、Type `*` 型にキャストします。  
  
##  <a name="allocator_base"></a>  allocator_base::allocator_base  
 `allocator_base` 型のオブジェクトを構築します。  
  
```
allocator_base();

template <class Other>  
allocator_base(const allocator_base<Other, Sync>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|コピーするアロケーター オブジェクト。|  
  
### <a name="remarks"></a>コメント  
 1 つ目のコンストラクターは、[allocator_base](../standard-library/allocator-base-class.md) インスタンスを構築します。 2 番目のコンストラクターは、`allocator_base<Type, _Sync>` インスタンス `a`、`allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a` などのいずれかに対し、`allocator_base` インスタンスを構築します。  
  
##  <a name="const_pointer"></a>  allocator_base::const_pointer  
 アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。  
  
```
typedef const Type *const_pointer;
```  
  
##  <a name="const_reference"></a>  allocator_base::const_reference  
 アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。  
  
```
typedef const Type& const_reference;
```  
  
##  <a name="construct"></a>  allocator_base::construct  
 指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。  
  
```
void construct(pointer ptr, const Type& val);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|オブジェクトが構築される場所へのポインター。|  
|`val`|構築されるオブジェクトが初期化される値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`new((void*)ptr Type(val)` を呼び出すことで、ユーザー定義のアロケーターに実装されます。  
  
##  <a name="deallocate"></a>  allocator_base::deallocate  
 指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。  
  
```
void deallocate(pointer ptr, size_type _Nx);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|  
|`_Nx`|記憶域から割り当てを解除されるオブジェクトの数。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`_Nx == 1` の場合は同期フィルター `Sync` で `deallocate(ptr)` を呼び出すことで、それ以外の場合は `operator delete(_Nx * ptr)` を呼び出すことで、ユーザー定義のアロケーターに実装されます。  
  
##  <a name="destroy"></a>  allocator_base::destroy  
 オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。  
  
```
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|破棄するオブジェクトのアドレスを指定するポインター。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`ptr->~Type()` を呼び出すことで、ユーザー定義のアロケーターに実装されます。  
  
##  <a name="difference_type"></a>  allocator_base::difference_type  
 アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。  
  
```
typedef std::ptrdiff_t difference_type;
```  
  
##  <a name="max_size"></a>  allocator_base::max_size  
 空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、型 `Type` の要素の数を返します。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 割り当てることができる要素の数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`0 < (size_t)-1 / sizeof(Type)` の場合は `(size_t)-1 / sizeof(Type)` を返すことで、それ以外は `1` を返すことで、ユーザー定義のアロケーターに実装されます。  
  
##  <a name="pointer"></a>  allocator_base::pointer  
 アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。  
  
```
typedef Type *pointer;
```  
  
##  <a name="reference"></a>  allocator_base::reference  
 アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。  
  
```
typedef Type& reference;
```  
  
##  <a name="size_type"></a>  allocator_base::size_type  
 テンプレート クラス `allocator_base` のオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。  
  
```
typedef std::size_t size_type;
```  
  
##  <a name="value_type"></a>  allocator_base::value_type  
 アロケーターによって管理される型。  
  
```
typedef Type value_type;
```  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




