---
title: "atomic 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 03665af409892b087bcc8a0858513f1f96f0c41d
ms.lasthandoff: 02/24/2017

---
# <a name="atomic-structure"></a>atomic 構造体
`Ty` 型の格納された値に対して分割不可能な操作を実行するオブジェクトについて記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[atomic::atomic コンストラクター](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|アトミック オブジェクトを構築します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[atomic::operator Ty 演算子](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|格納されている値を読み取って返します。 ([atomic::load メソッド](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[atomic::operator= 演算子](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|格納されている値を置き換えるために指定された値を使用します。 ([atomic::store メソッド](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[atomic::operator++ 演算子](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator+= 演算子](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|指定した値を格納されている値に加算します。 整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator-- 演算子](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator-= 演算子](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|指定した値を格納されている値から減算します。 整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator&= 演算子](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|指定されている値と格納されている値に対して、ビットごとの `and` を実行します。 整数の特殊化でのみ使用されます。|  
|[atomic::operator&#124;= 演算子](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|指定されている値と格納されている値に対して、ビットごとの `or` を実行します。 整数の特殊化でのみ使用されます。|  
|[atomic::operator^= 演算子](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|指定されている値と格納されている値に対して、ビットごとの `exclusive or` を実行します。 整数の特殊化でのみ使用されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[atomic::compare_exchange_strong メソッド](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|`atomic_compare_and_exchange` に対して `this` 操作を実行し、その結果を返します。|  
|[atomic::compare_exchange_weak メソッド](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|`weak_atomic_compare_and_exchange` に対して `this` 操作を実行し、その結果を返します。|  
|[atomic::fetch_add メソッド](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|指定した値を格納されている値に加算します。|  
|[atomic::fetch_and メソッド](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|指定されている値と格納されている値に対して、ビットごとの `and` を実行します。|  
|[atomic::fetch_or メソッド](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|指定されている値と格納されている値に対して、ビットごとの `or` を実行します。|  
|[atomic::fetch_sub メソッド](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|指定した値を格納されている値から減算します。|  
|[atomic::fetch_xor メソッド](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|指定されている値と格納されている値に対して、ビットごとの `exclusive or` を実行します。|  
|[atomic::is_lock_free メソッド](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|`this` に対するアトミック操作が*ロック制御不要*であるかどうかを指定します。 その型に対する分割不可能な操作においてロックが使用される場合、atomic 型は*ロック制御不要*になります。|  
|[atomic::load メソッド](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|格納されている値を読み取って返します。|  
|[atomic::store メソッド](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|格納されている値を置き換えるために指定された値を使用します。|  
  
## <a name="remarks"></a>コメント  
 `Ty` 型は、*普通にコピー可能*である必要があります。 つまり、[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) を使用してそのバイトをコピーした場合は、元のオブジェクトに等しい有効な `Ty` オブジェクトが生成される必要があります。 `compare_exchange_weak` および `compare_exchange_strong` のメンバー関数は、[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) を使用して&2; つの `Ty` 値が等しいかどうかを判断します。 これらの関数は、`Ty` 定義の `operator==` を使用しません。 `atomic` のメンバー関数は、`memcpy` を使用して `Ty` 型の値をコピーします。  
  
 部分的特殊化 `atomic<Ty *>` は、すべてのポインター型において存在します。 特殊化により、マネージ ポインター値のオフセットの加算またはマネージ ポインター値からのオフセットの減算が可能になります。 算術演算は `ptrdiff_t` 型の引数を受け取り、通常のアドレス算術演算との一貫性を保つように `Ty` のサイズに従ってその引数を調整します。  
  
 特殊化は、`bool` を除くすべての整数型において存在します。 それぞれの特殊化には、分割不可能な算術演算および論理演算のための豊富な一連のメソッドが用意されています。  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 整数の特殊化は、対応する `atomic_``integral` 型から派生します。 たとえば、`atomic<unsigned int>` は `atomic_uint` から派生します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atomic  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<atomic>](../standard-library/atomic.md)   
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)




