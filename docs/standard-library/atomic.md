---
title: "&lt;atomic&gt; | Microsoft Docs"
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
  - "<atomic>"
  - "atomic/std::atomic_int_least32_t"
  - "atomic/std::atomic_ullong"
  - "atomic/std::atomic_ptrdiff_t"
  - "atomic/std::atomic_char16_t"
  - "atomic/std::atomic_schar"
  - "atomic/std::atomic_ulong"
  - "atomic/std::atomic_uint_fast32_t"
  - "atomic/std::atomic_uint8_t"
  - "atomic/std::atomic_int32_t"
  - "atomic/std::atomic_uint_fast64_t"
  - "atomic/std::atomic_uint32_t"
  - "atomic/std::atomic_int16_t"
  - "atomic/std::atomic_uintmax_t"
  - "atomic/std::atomic_intmax_t"
  - "atomic/std::atomic_long"
  - "atomic/std::atomic_int"
  - "atomic/std::atomic_uint_least8_t"
  - "atomic/std::atomic_size_t"
  - "atomic/std::atomic_uint_fast16_t"
  - "atomic/std::atomic_wchar_t"
  - "atomic/std::atomic_int_fast64_t"
  - "atomic/std::atomic_uint_fast8_t"
  - "atomic/std::atomic_int_fast8_t"
  - "atomic/std::atomic_intptr_t"
  - "atomic/std::atomic_uint"
  - "atomic/std::atomic_uint16_t"
  - "atomic/std::atomic_char32_t"
  - "atomic/std::atomic_uint64_t"
  - "atomic/std::atomic_ushort"
  - "atomic/std::atomic_int_least16_t"
  - "atomic/std::atomic_char"
  - "atomic/std::atomic_uint_least32_t"
  - "atomic/std::atomic_uintptr_t"
  - "atomic/std::atomic_short"
  - "atomic/std::atomic_llong"
  - "atomic/std::atomic_uint_least16_t"
  - "atomic/std::atomic_int_fast16_t"
  - "atomic/std::atomic_int_least8_t"
  - "atomic/std::atomic_int_least64_t"
  - "atomic/std::atomic_int_fast32_t"
  - "atomic/std::atomic_uchar"
  - "atomic/std::atomic_int8_t"
  - "atomic/std::atomic_int64_t"
  - "atomic/std::atomic_uint_least64_t"
dev_langs: 
  - "C++"
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;atomic&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスとテンプレート クラスを分割不可能な操作をサポートする型を作成することです。  
  
## 構文  
  
```cpp  
#include <atomic>  
```  
  
## 解説  
  
> [!NOTE]
>  **\/clr** または **\/clr:pure**を使用してコンパイルされたコードでは、このヘッダーはブロックされます。  
  
 分割不可能な操作に正しくミューテックス ロックを使用せずに、オブジェクトを処理するために、複数のスレッドに使用できる 2 種類のキー プロパティがあります。  
  
-   分割不可能な操作が不可分であるため、別のスレッドが同じオブジェクトの 2 番目の分割不可能な操作は、最初の分割不可能な操作の前または後にのみオブジェクトの状態を取得できます。  
  
-   [memory\_order](../Topic/memory_order%20Enum.md) の引数に基づいて、分割不可能な操作は、同じスレッドで他の分割不可能な操作の効果の表示の順序の必要条件を設定します。  その結果、順序の要件に違反するコンパイラの最適化を禁じます。  
  
 一部のプラットフォームで、効率的に `mutex` ロックを使用しない型の分割不可能な操作を実装することができない場合があります。  原子型はその型の分割不可能な操作がロックを使用すると、*ロック制御なし* です。  
  
 クラス [atomic\_flag](../Topic/atomic_flag%20Structure.md) は `bool` フラグを保持する最小の原子型を提供します。  この操作は常にロック制御不要です。  
  
 テンプレート クラス `atomic<Ty>` は引数の型 `Ty` オブジェクトを保存し、格納されている値への分割不可能なアクセスを提供します。  [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) を使用してコピーされ、等値に [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)を使用してテストできる型でインスタンス化することができます。  特に、浮動小数点型でそれらの要件は、多くの場合、塗りつぶすユーザー定義型を使用できます。  
  
 テンプレートには、一連の整数型の特化型、ポインターの部分的な特化があります。  これらのクラスは、プライマリ テンプレートで使用できない追加操作を提供します。  
  
## ポインターの特化型  
 `atomic<Ty *>` の部分的特殊化がすべてのポインター型に適用されます。  これらはポインター演算にメソッドを提供します。  
  
## 必要なクラス  
 `atomic<integral>` の特殊化をすべての整数型に適用されます。  これらはプライマリ テンプレートで使用できない追加操作を提供します。  
  
 `atomic<integral>` の各型には、その型の操作は、ロック制御なしであるかどうかをコンパイル時に決定するために、`if directive` で使用可能な対応のマクロがあります。  マクロの値がゼロの場合、型の操作は、ロック制御なしではありません。  値が 1 の場合、アクションはロック制御不要になる可能性があります。ランタイム チェックが必要です。  値が 2 の場合、アクションはロック制御不要です。  型の操作がロックがないかどうかを実行時に確認するには `atomic_is_lock_free` 関数を使用できます。  
  
 整数型のそれぞれについて、その整数型のオブジェクトを管理する、対応する名前付き原子型があります。  `atomic_integral` の各型に `atomic<Ty>` の対応するインスタンス化にメンバー関数のセットがあり、非メンバーの分離不可能な状態関数に渡すことができます。  
  
|`atomic_integral` の型|整数型|`atomic_is_lock_free` マクロ|  
|--------------------------|---------|-------------------------------|  
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|  
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|  
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|  
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|  
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|  
  
 Typedef 名はヘッダー \<inttypes.h で定義されている型の部分に分割不可能なテンプレートの特殊化にあります。\>  
  
|原子型|Typedef 名|  
|---------|---------------|  
|`atomic_int8_t`|`atomic<int8_t>`|  
|`atomic_uint8_t`|`atomic<uint8_t>`|  
|`atomic_int16_t`|`atomic<int16_t>`|  
|`atomic_uint16_t`|`atomic<uint16_t>`|  
|`atomic_int32_t`|`atomic<int32_t>`|  
|`atomic_uint32_t`|`atomic<uint32_t>`|  
|`atomic_int64_t`|`atomic<int64_t>`|  
|`atomic_uint64_t`|`atomic<uint64_t>`|  
|`atomic_int_least8_t`|`atomic<int_least8_t>`|  
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|  
|`atomic_int_least16_t`|`atomic<int_least16_t>`|  
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|  
|`atomic_int_least32_t`|`atomic<int_least32_t>`|  
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|  
|`atomic_int_least64_t`|`atomic<int_least64_t>`|  
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|  
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|  
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|  
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|  
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|  
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|  
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|  
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|  
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|  
|`atomic_intptr_t`|`atomic<intptr_t>`|  
|`atomic_uintptr_t`|`atomic<uintptr_t>`|  
|`atomic_size_t`|`atomic<size_t>`|  
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|  
|`atomic_intmax_t`|`atomic<intmax_t>`|  
|`atomic_uintmax_t`|`atomic<uintmax_t>`|  
  
## 構造体  
  
|名前|説明|  
|--------|--------|  
|[atomic 構造体](../standard-library/atomic-structure.md)|格納されている値の分割不可能な操作を実行するオブジェクトを表します。|  
|[atomic\_flag 構造体](../Topic/atomic_flag%20Structure.md)|`bool` フラグをアトミックに設定およびクリアするオブジェクトについて記述します。|  
  
## 列挙型  
  
|名前|説明|  
|--------|--------|  
|[memory\_order 列挙型](../Topic/memory_order%20Enum.md)|メモリ位置に対する同期操作のシンボル名を提供します。  これらの操作は、1 つのスレッドの割り当てが別のスレッドにおいて表示される方法に影響します。|  
  
## 関数  
 次の一覧では、`_explicit` でない関数に対応する `_explicit`セマンティクス、があります `memory_order_seq_cst`の [memory\_order](../Topic/memory_order%20Enum.md) の暗黙の引数があります。  
  
|名前|説明|  
|--------|--------|  
|[atomic\_compare\_exchange\_strong 関数](../Topic/atomic_compare_exchange_strong%20Function.md)|*アトミックの比較および交換*の操作を実行します。|  
|[atomic\_compare\_exchange\_strong\_explicit 関数](../Topic/atomic_compare_exchange_strong_explicit%20Function.md)|*アトミックの比較および交換*の操作を実行します。|  
|[atomic\_compare\_exchange\_weak 関数](../Topic/atomic_compare_exchange_weak%20Function.md)|*弱いアトミックの比較および交換*の操作を実行します。|  
|[atomic\_compare\_exchange\_weak\_explicit 関数](../Topic/atomic_compare_exchange_weak_explicit%20Function.md)|*弱いアトミックの比較および交換*の操作を実行します。|  
|[atomic\_exchange 関数](../Topic/atomic_exchange%20Function.md)|格納されている値を置き換えます。|  
|[atomic\_exchange\_explicit 関数](../Topic/atomic_exchange_explicit%20Function.md)|格納されている値を置き換えます。|  
|[atomic\_fetch\_add 関数](../Topic/atomic_fetch_add%20Function.md)|既存の格納値に指定された値を追加します。|  
|[atomic\_fetch\_add\_explicit 関数](../Topic/atomic_fetch_add_explicit%20Function.md)|既存の格納値に指定された値を追加します。|  
|[atomic\_fetch\_and 関数](../Topic/atomic_fetch_and%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `and` を実行します。|  
|[atomic\_fetch\_and\_explicit 関数](../Topic/atomic_fetch_and_explicit%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `and` を実行します。|  
|[atomic\_fetch\_or 関数](../Topic/atomic_fetch_or%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `or` を実行します。|  
|[atomic\_fetch\_or\_explicit 関数](../Topic/atomic_fetch_or_explicit%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `or` を実行します。|  
|[atomic\_fetch\_sub 関数](../Topic/atomic_fetch_sub%20Function.md)|既存の格納される値から指定された値を減算します。|  
|[atomic\_fetch\_sub\_explicit 関数](../Topic/atomic_fetch_sub_explicit%20Function.md)|既存の格納される値から指定された値を減算します。|  
|[atomic\_fetch\_xor 関数](../Topic/atomic_fetch_xor%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `exclusive or` を実行します。|  
|[atomic\_fetch\_xor\_explicit 関数](../Topic/atomic_fetch_xor_explicit%20Function.md)|指定できる値と既存の格納されている値のビットごとのな `exclusive or` を実行します。|  
|[atomic\_flag\_clear 関数](../Topic/atomic_flag_clear%20Function.md)|`false`への `atomic_flag` オブジェクトにフラグを設定します。|  
|[atomic\_flag\_clear\_explicit 関数](../Topic/atomic_flag_clear_explicit%20Function.md)|`false`への `atomic_flag` オブジェクトにフラグを設定します。|  
|[atomic\_flag\_test\_and\_set 関数](../Topic/atomic_flag_test_and_set%20Function.md)|`true`への `atomic_flag` オブジェクトにフラグを設定します。|  
|[atomic\_flag\_test\_and\_set\_explicit 関数](../Topic/atomic_flag_test_and_set_explicit%20Function.md)|`true`への `atomic_flag` オブジェクトにフラグを設定します。|  
|[atomic\_init 関数](../Topic/atomic_init%20Function.md)|`atomic` オブジェクトに格納されている値を設定します。|  
|[atomic\_is\_lock\_free 関数](../Topic/atomic_is_lock_free%20Function.md)|指定されたオブジェクトの分割不可能な操作がロックがないかどうかを指定します。|  
|[atomic\_load 関数](../Topic/atomic_load%20Function.md)|アトミックに値を取得します。|  
|[atomic\_load\_explicit 関数](../Topic/atomic_load_explicit%20Function.md)|アトミックに値を取得します。|  
|[atomic\_signal\_fence 関数](../Topic/atomic_signal_fence%20Function.md)|同じスレッドで実行されるシグナル ハンドラーがある呼び出し元のスレッドにメモリ フェンス間の命令の要件を確立する *フェンス全体* として機能します。|  
|[atomic\_store 関数](../Topic/atomic_store%20Function.md)|アトミックに値を格納します。|  
|[atomic\_store\_explicit 関数](../Topic/atomic_store_explicit%20Function.md)|アトミックに値を格納します。|  
|[atomic\_thread\_fence 関数](../Topic/atomic_thread_fence%20Function.md)|他のメモリ フェンス全体に対して強制的な要件を確立する *フェンス全体* として機能します。|  
|[kill\_dependency 関数](../Topic/kill_dependency%20Function.md)|可能な依存関係チェーンを中断します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)