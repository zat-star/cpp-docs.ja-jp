---
title: "atomic 構造体 | Microsoft Docs"
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
  - "atomic/std::atomic"
dev_langs: 
  - "C++"
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atomic 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Ty` 型の格納された値に対して分割不可能な操作を実行するオブジェクトについて記述します。  
  
## 構文  
  
```  
template <class Ty>  
struct atomic;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[atomic::atomic コンストラクター](../Topic/atomic::atomic%20Constructor.md)|アトミック オブジェクトを構築します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[atomic::operator Ty 演算子](../Topic/atomic::operator%20Ty%20Operator.md)|格納されている値を読み取って返します。\([atomic::load メソッド](../Topic/atomic::load%20Method.md)\)|  
|[atomic::operator\= 演算子](../Topic/atomic::operator=%20Operator.md)|格納されている値を置き換えるために指定された値を使用します。\([atomic::store メソッド](../Topic/atomic::store%20Method.md)\)|  
|||  
|[atomic::operator\+\+ 演算子](../Topic/atomic::operator++%20Operator.md)|格納されている値をインクリメントします。  整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator\+\= 演算子](../Topic/atomic::operator+=%20Operator.md)|指定した値を格納されている値に加算します。  整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator\-\- 演算子](../Topic/atomic::operator--%20Operator.md)|格納されている値をデクリメントします。  整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator\-\= 演算子](../Topic/atomic::operator-=%20Operator.md)|指定した値を格納されている値から減算します。  整数およびポインターの特殊化でのみ使用されます。|  
|[atomic::operator&\= 演算子](../Topic/atomic::operator&=%20Operator.md)|指定されている値と格納されている値に対して、ビットごとの `and` を実行します。  整数の特殊化でのみ使用されます。|  
|[atomic::operator&#124;\= 演算子](../Topic/atomic::operator%7C=%20Operator.md)|指定されている値と格納されている値に対して、ビットごとの `or` を実行します。  整数の特殊化でのみ使用されます。|  
|[atomic::operator^\= 演算子](../Topic/atomic::operator%5E=%20Operator.md)|指定されている値と格納されている値に対して、ビットごとの `exclusive or` を実行します。  整数の特殊化でのみ使用されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[atomic::compare\_exchange\_strong メソッド](../Topic/atomic::compare_exchange_strong%20Method.md)|`this` に対して `atomic_compare_and_exchange` 操作を実行し、その結果を返します。|  
|[atomic::compare\_exchange\_weak メソッド](../Topic/atomic::compare_exchange_weak%20Method.md)|`this` に対して `weak_atomic_compare_and_exchange` 操作を実行し、その結果を返します。|  
|[atomic::fetch\_add メソッド](../Topic/atomic::fetch_add%20Method.md)|指定した値を格納されている値に加算します。|  
|[atomic::fetch\_and メソッド](../Topic/atomic::fetch_and%20Method.md)|指定されている値と格納されている値に対して、ビットごとの `and` を実行します。|  
|[atomic::fetch\_or メソッド](../Topic/atomic::fetch_or%20Method.md)|指定されている値と格納されている値に対して、ビットごとの `or` を実行します。|  
|[atomic::fetch\_sub メソッド](../Topic/atomic::fetch_sub%20Method.md)|指定した値を格納されている値から減算します。|  
|[atomic::fetch\_xor メソッド](../Topic/atomic::fetch_xor%20Method.md)|指定されている値と格納されている値に対して、ビットごとの `exclusive or` を実行します。|  
|[atomic::is\_lock\_free メソッド](../Topic/atomic::is_lock_free%20Method.md)|`this` に対する分割不可能な操作が*ロック制御不要*であるかどうかを指定します。  その型に対する分割不可能な操作においてロックが使用される場合、atomic 型は*ロック制御不要*になります。|  
|[atomic::load メソッド](../Topic/atomic::load%20Method.md)|格納されている値を読み取って返します。|  
|[atomic::store メソッド](../Topic/atomic::store%20Method.md)|格納されている値を置き換えるために指定された値を使用します。|  
  
## 解説  
 `Ty` 型は、*普通にコピー可能*である必要があります。  つまり、[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) を使用してそのバイトをコピーした場合は、元のオブジェクトに等しい有効な `Ty` オブジェクトが生成される必要があります。  `compare_exchange_weak` および `compare_exchange_strong` のメンバー関数は、[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) を使用して 2 つの `Ty` 値が等しいかどうかを判断します。  これらの関数は、`Ty` 定義の `operator==` を使用しません。  `atomic` のメンバー関数は、`memcpy` を使用して `Ty` 型の値をコピーします。  
  
 部分的特殊化 `atomic<Ty *>` は、すべてのポインター型において存在します。  特殊化により、マネージ ポインター値のオフセットの加算またはマネージ ポインター値からのオフセットの減算が可能になります。  算術演算は `ptrdiff_t` 型の引数を受け取り、通常のアドレス算術演算との一貫性を保つように `Ty` のサイズに従ってその引数を調整します。  
  
 特殊化は、`bool` を除くすべての整数型において存在します。  それぞれの特殊化には、分割不可能な算術演算および論理演算のための豊富な一連のメソッドが用意されています。  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 整数の特殊化は、対応する `atomic_``integral` 型から派生します。  たとえば、`atomic<unsigned int>` は `atomic_uint` から派生します。  
  
## 必要条件  
 **ヘッダー:** atomic  
  
 **名前空間:** std  
  
## 参照  
 [\<atomic\>](../standard-library/atomic.md)   
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)