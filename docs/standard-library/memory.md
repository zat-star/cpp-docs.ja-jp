---
title: "&lt;memory&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::<memory>"
  - "std.<memory>"
  - "<memory>"
  - "std::<memory>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory ヘッダー"
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;memory&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メモリの割り当てとオブジェクトの解放を支援するクラス、演算子、および各種テンプレートを定義します。  
  
## 構文  
  
```  
  
#include <memory>  
  
```  
  
## メンバー  
  
### Functions  
  
|||  
|-|-|  
|[addressof](../Topic/addressof.md)|オブジェクトの実際のアドレスを取得します。|  
|[align](../Topic/align.md)|指定されたアラインメントと開始アドレスに基づいて特定のサイズの範囲へのポインターを返します。|  
|[allocate\_shared](../Topic/allocate_shared.md)|指定されたアロケーターを使用し、特定の型に割り当てられ構築されたオブジェクトに対して  `shared_ptr` を作成します。|  
|[checked\_uninitialized\_copy](../misc/checked-uninitialized-copy.md)|`uninitialized_copy` と同じですが、出力反復子としてチェックを行う反復子の使用を強制します。|  
|[checked\_uninitialized\_fill\_n](../misc/checked-uninitialized-fill-n.md)|`uninitialized_fill_n` と同じですが、出力反復子としてチェックを行う反復子の使用を強制します。|  
|[const\_pointer\_cast](../Topic/const_pointer_cast.md)|`shared_ptr` への定数キャストを行います。|  
|[declare\_no\_pointers](../Topic/declare_no_pointers.md)|指定されたアドレスを先頭とする指定されたブロック サイズの範囲内にある文字が、追跡可能なポインターを含まないことをガベージ コレクターに通知します。|  
|[declare\_reachable](../Topic/declare_reachable.md)|指定されたアドレスが、割り当てられたストレージのアドレスであり、そのストレージに到達可能であることをガベージ コレクションに通知します。|  
|[default\_delete](../Topic/default_delete.md)|`operator new` を使用して割り当てられたオブジェクトを削除します。  `unique_ptr` での使用に適しています。|  
|[dynamic\_pointer\_cast](../Topic/dynamic_pointer_cast.md)|`shared_ptr` への動的キャストを行います。|  
|[get\_deleter](../Topic/get_deleter%20Function.md)|`shared_ptr` から削除子を取得します。|  
|[get\_pointer\_safety](../Topic/get_pointer_safety.md)|ガベージ コレクターが想定するポインターの安全性の種類を返します。|  
|[get\_temporary\_buffer](../Topic/get_temporary_buffer.md)|指定した要素数を上限とする要素シーケンスに対し、一時的なストレージを割り当てます。|  
|[make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md)|既定のアロケーターを使用してゼロ以上の引数から構築された割り当て済みオブジェクトを指し示す `shared_ptr` を作成し、返します。|  
|[make\_unique](../Topic/make_unique.md)|ゼロ以上の引数から構築された割り当て済みオブジェクトを指し示す [unique\_ptr](../standard-library/unique-ptr-class.md) を作成し、返します。|  
|[owner\_less](../Topic/owner_less.md)|共有ポインターとウィーク ポインターの所有権ベースの混合型比較を実行します。|  
|[pointer\_safety](../Topic/pointer_safety%20Enumeration.md)|`get_pointer_safety` のすべての可能な戻り値の列挙体です。|  
|[return\_temporary\_buffer](../Topic/return_temporary_buffer.md)|`get_temporary_buffer` テンプレート関数を使用して割り当てられた一時メモリを解放します。|  
|[static\_pointer\_cast](../Topic/static_pointer_cast.md)|`shared_ptr` への静的キャストを行います。|  
|[swap](../Topic/swap%20\(C++%20Standard%20Library\).md)|2 つの `shared_ptr` または `weak_ptr` オブジェクトを交換します。|  
|[unchecked\_uninitialized\_copy](../Topic/unchecked_uninitialized_copy.md)|`uninitialized_copy` と同じですが、\_SECURE\_SCL\=1 が定義されているときに、出力反復子としてチェックを行わない反復子を使用できます。|  
|[unchecked\_uninitialized\_fill\_n](../misc/unchecked-uninitialized-fill-n.md)|`uninitialized_fill_n` と同じですが、\_SECURE\_SCL\=1 が定義されているときに、出力反復子としてチェックを行わない反復子を使用できます。|  
|[undeclare\_no\_pointers](../Topic/undeclare_no_pointers.md)|ベース アドレス ポインターとブロック サイズで定義されたメモリ ブロック内の文字が、追跡可能なポインターを含む可能性があることをガベージ コレクターに通知します。|  
|[undeclare\_reachable](../Topic/undeclare_reachable.md)|指定されたメモリ位置に到達できないことを `garbage_collector` に通知します。|  
|[uninitialized\_copy](../Topic/uninitialized_copy.md)|指定された入力範囲にあるオブジェクトを、初期化されていないコピー先の範囲にコピーします。|  
|[uninitialized\_copy\_n](../Topic/uninitialized_copy_n.md)|入力反復子から、指定した数の要素のコピーを作成します。  コピーは前方反復子に格納されます。|  
|[uninitialized\_fill](../Topic/uninitialized_fill.md)|指定された値のオブジェクトを、初期化されていないコピー先の範囲にコピーします。|  
|[uninitialized\_fill\_n](../Topic/uninitialized_fill_n.md)|指定された値のオブジェクトを、初期化されていないコピー先の範囲にある指定された数の要素にコピーします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cmemory%3E\).md)|指定したクラスのアロケーター オブジェクト間の非等値をテストします。|  
|[operator\=\=](../Topic/operator==%20\(%3Cmemory%3E\).md)|指定したクラスのアロケーター オブジェクト間の等値をテストします。|  
|[\>\= 演算子](../Topic/operator%3E=%20\(%3Cmemory%3E\).md)|指定したクラスの 1 つ目のアロケーター オブジェクトが 2 つ目のアロケーター オブジェクト以上であるかどうかをテストします。|  
|[\< 演算子](../Topic/operator%3C%20\(%3Cmemory%3E\).md)|指定したクラスの 1 つ目のオブジェクトが 2 つ目のオブジェクト未満であるかどうかをテストします。|  
|[\<\= 演算子](../Topic/operator%3C=%20\(%3Cmemory%3E\).md)|指定したクラスの 1 つ目のオブジェクトが 2 つ目のオブジェクト以下であるかどうかをテストします。|  
|[\> 演算子](../Topic/operator%3E%20\(%3Cmemory%3E\).md)|指定したクラスの 1 つ目のオブジェクトが 2 つ目のオブジェクトを超えるかどうかをテストします。|  
|[演算子 \<\<](../Topic/operator%3C%3C%20\(%3Cmemory%3E\).md)|`shared_ptr` の挿入演算子です。|  
  
### クラス  
  
|||  
|-|-|  
|[allocator](../standard-library/allocator-class.md)|このテンプレート クラスは、**Type** 型のオブジェクトの配列に対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|  
|[allocator\_traits](../Topic/allocator_traits%20Class.md)|アロケーター対応のコンテナーが必要とするすべての情報を指定したオブジェクトを記述します。|  
|[auto\_ptr](../standard-library/auto-ptr-class.md)|このテンプレート クラスは、**Type \*** 型の割り当てられたオブジェクトを指すポインターを格納し、それが指すオブジェクトを囲んでいる auto\_ptr が破棄されたときに、そのオブジェクトを確実に破棄するオブジェクトを記述します。|  
|[bad\_weak\_ptr](../standard-library/bad-weak-ptr-class.md)|weak\_ptr が無効であることを示す例外を報告します。|  
|[enabled\_shared\_from\_this](../standard-library/enable-shared-from-this-class.md)|`shared_ptr` の生成を支援します。|  
|[pointer\_traits](../standard-library/pointer-traits-struct.md)|`allocator_traits` テンプレート クラスのオブジェクトが、ポインター型 `Ptr` を持つアロケーターを記述するために必要とする情報を提供します。|  
|[raw\_storage\_iterator](../Topic/raw_storage_iterator%20Class.md)|アルゴリズムの結果を初期化されていないメモリに格納するために用意されたアダプター クラスです。|  
|[shared\_ptr](../standard-library/shared-ptr-class.md)|参照カウント スマート ポインターを、動的に割り当てられたオブジェクトにラップします。|  
|[unique\_ptr](../standard-library/unique-ptr-class.md)|所有されているオブジェクトへのポインターを格納します。  このポインターは、この `unique_ptr` によってのみ所有されます。  `unique_ptr` は所有者が破棄されたときに破棄されます。|  
|[weak\_ptr](../standard-library/weak-ptr-class.md)|関連付けの弱いポインターをラップします。|  
  
### 特殊化  
  
|||  
|-|-|  
|[allocator\<void\>](../standard-library/allocator-void-class.md)|void 型へのテンプレート クラスのアロケーターを特殊化し、この特殊なコンテキストで意味を持つメンバー型のみを定義します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)