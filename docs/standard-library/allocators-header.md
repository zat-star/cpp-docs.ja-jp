---
title: "&lt;allocators&gt; | Microsoft Docs"
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
  - "stdext::<allocators>"
  - "allocators/stdext::allocators"
  - "<allocators>"
  - "stdext.<allocators>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocators ヘッダー"
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;allocators&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

割り当てることができるメモリはノード ベース コンテナーの間ブロック各種テンプレートを定義します。  
  
## 構文  
  
```  
#include <allocators>  
```  
  
## 解説  
 \<アロケーターの\> ヘッダーはノード ベース コンテナーに管理方法を選択するために使用できる 6 種類のテンプレートが用意されています。  これらのテンプレートで使用することも、さまざまなマルチスレッド スキームに管理方法を調整する、さまざまな同期フィルターを提供します。この情報には、なし\)。  既知のメモリ使用パターンにメモリ管理の方法と、特定のアプリケーションの同期要件、一致させる場合は、速度を増やすか、アプリケーション全体のメモリ要件を単純化するできます。  
  
 アロケーターのテンプレートは追加管理方法を提供するために、カスタマイズや置換できる再利用可能なコンポーネントに実装されます。  
  
 標準 C\+\+ ライブラリ \(std::list、std::set、std::multiset、std::map と std::multimap\) のノード ベース コンテナーは個々のノードで要素が格納されます。  特定のコンテナー型のすべてのノードは同じサイズであるため、汎用のメモリ マネージャーの柔軟性は必要ではありません。  メモリ ブロックのサイズがコンパイル時に認識されるため、メモリ マネージャーは、よりもはるかに簡単です。  
  
 ノード ベースではないコンテナーで使用されるときに \(標準 C\+\+ ライブラリのコンテナーの std::vector の std::deque と std::basic\_string など\)、alllocator のテンプレートは正しく動作しますが、既定のアロケーターよりもパフォーマンスが向上するように耐えられないでしょう。  
  
 アロケーターは指定型のオブジェクトおよび配列の記憶割振エラーと解放を管理するオブジェクトを表すテンプレート クラスです。  アロケーター オブジェクトは、標準 C\+\+ ライブラリのいくつかのコンテナーのテンプレート クラスによって使用されます。  
  
 アロケーターはこの型のすべてのテンプレートが:  
  
 `template<class`  `Type` `>`  
  
 `class allocator;`  
  
 テンプレートの引数が `Type` アロケーターのインスタンスによって管理されている型です。  標準 C\+\+ ライブラリは既定のアロケーター、[\<memory\>](../standard-library/memory.md)で定義されたテンプレート [アロケーター](../standard-library/allocator-class.md)クラスを提供します。  \<アロケーターの\> ヘッダーは次のアロケーターを提供し、T:  
  
-   [allocator\_newdel](../standard-library/allocator-newdel-class.md)  
  
-   [allocator\_unbounded](../standard-library/allocator-unbounded-class.md)  
  
-   [allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)  
  
-   [allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)  
  
-   [allocator\_suballoc](../standard-library/allocator-suballoc-class.md)  
  
-   [allocator\_chunklist](../Topic/allocator_chunklist%20Class.md)  
  
 次のコード例などのコンテナーを作成した場合、2 番目の型引数としてアロケーターの適切なインスタンス化を使用します。  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`  
  
 \_List0 は `allocator_chunklist` と既定の同期フィルターを持つノードを割り当てます。  
  
 既定以外の同期フィルターによってアロケーターのテンプレートを作成するには [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) マクロの使用:  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`  
  
 `std::list<int, alloc<int> > _List1;`  
  
 \_Lst1 は `allocator_chunklist` と [sync\_per\_thread](../standard-library/sync-per-thread-class.md) の同期フィルターを持つノードを割り当てます。  
  
 ブロックのアロケーターはキャッシュまたはフィルターです。  キャッシュは、型の std::size\_t の 1 個の引数を受け取るテンプレート クラスです。  これは、単一のサイズのメモリ ブロックの割り当てと解放するブロックのアロケーターを定義します。  これは、演算子を使用して `new`メモリを取得する必要がありますが、各ブロックの演算子に `new` 別の呼び出しを行う必要はありません。  これは、以降の再割り当ての大きなキャッシュによって解放されるブロックからなど、suballocate 可能性があります。  
  
 再コンパイルできないをコンパイラによってテンプレートではない、キャッシュのメンバー関数に渡された引数の\_Sz 値の割り当てと解放するときインスタンス化されたか std::size\_t の引数の値が使用されます。  
  
 \<アロケーターは\> 次のキャッシュ テンプレートを提供し、T:  
  
-   [cache\_freelist](../standard-library/cache-freelist-class.md)  
  
-   [cache\_suballoc](../standard-library/cache-suballoc-class.md)  
  
-   [cache\_chunklist](../standard-library/cache-chunklist-class.md)  
  
 フィルターは、テンプレート引数として渡された別のブロックのアロケーターを使用してメンバー関数を実装するブロックのアロケーターです。  フィルターの一般的なフォームは別のブロックのインスタンスのメンバー関数のアクセス制御に同期ポリシーを適用する同期フィルターです。\<アロケーターは\> 次の同期フィルターを提供し、T:  
  
-   [sync\_none](../standard-library/sync-none-class.md)  
  
-   [sync\_per\_container](../standard-library/sync-per-container-class.md)  
  
-   [sync\_per\_thread](../standard-library/sync-per-thread-class.md)  
  
-   [sync\_shared](../Topic/sync_shared%20Class.md)  
  
 \<アロケーターは\> 複数のブロックのアロケーターをインスタンスに、コンパイル時ではなく実行時に割り当てや解放として使用されるインスタンスをを保持するフィルター [rts\_alloc](../standard-library/rts-alloc-class.md)を提供します。  これは再コンパイルできないをコンパイラで使用されます。  
  
 同期ポリシーはどのようにアロケーターのインスタンス ハンドル複数のスレッドから同時に割り当ておよび解放の要求を判断します。  最も単純なポリシーは同期管理を離れたユーザーへの基になるキャッシュ オブジェクトに対するすべての要求を直接渡すことです。  より複雑なポリシーは、基になるキャッシュ オブジェクトへのアクセスをシリアル化するには、ミューテックスを使用することができます。  
  
 コンパイラはコンパイルのシングルスレッドとマルチスレッド アプリケーションの両方をサポートする場合は、シングルスレッド アプリケーションの既定の同期フィルターは `sync_none`;です 他のすべての場合には `sync_shared`です。  
  
 キャッシュ テンプレート `cache_freelist` は空きリストに格納される要素の最大数を決定する最大クラスの引数を受け取ります。  
  
 \<アロケーターは\> 次の最大クラスを提供し、T:  
  
-   [max\_none](../Topic/max_none%20Class.md)  
  
-   [max\_unbounded](../standard-library/max-unbounded-class.md)  
  
-   [max\_fixed\_size](../standard-library/max-fixed-size-class.md)  
  
-   [max\_variable\_size](../standard-library/max-variable-size-class.md)  
  
### \[マクロ\]  
  
|||  
|-|-|  
|[ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)|アロケーターのテンプレート クラスについて説明します。|  
|[CACHE\_CHUNKLIST](../Topic/CACHE_CHUNKLIST%20\(%3Callocators%3E\).md)|`stdext::allocators::cache_chunklist<sizeof(Type)>`を紹介します。|  
|[CACHE\_FREELIST](../Topic/CACHE_FREELIST%20\(%3Callocators%3E\).md)|`stdext::allocators::cache_freelist<sizeof(Type), max>`を紹介します。|  
|[CACHE\_SUBALLOC](../Topic/CACHE_SUBALLOC%20\(%3Callocators%3E\).md)|`stdext::allocators::cache_suballoc<sizeof(Type)>`を紹介します。|  
|[SYNC\_DEFAULT](../Topic/SYNC_DEFAULT%20\(%3Callocators%3E\).md)|同期フィルターを紹介します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Callocators%3E\).md)|指定したクラスのアロケーター オブジェクト間の非等値をテストします。|  
|[operator\=\=](../Topic/operator==%20\(%3Callocators%3E\).md)|指定したクラスのアロケーター オブジェクト間の等値をテストします。|  
  
### クラス  
  
|||  
|-|-|  
|[allocator\_base](../standard-library/allocator-base-class.md)|同期フィルターからユーザー定義のアロケーターを作成するために必要な基本クラスと共通の機能を定義します。|  
|[allocator\_chunklist](../Topic/allocator_chunklist%20Class.md)|型 [cache\_chunklist](../standard-library/cache-chunklist-class.md)のキャッシュを使用してオブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。|  
|[allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)|[max\_fixed\_size](../standard-library/max-fixed-size-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。|  
|[allocator\_newdel](../standard-library/allocator-newdel-class.md)|メモリ ブロックと `operator new` を解放するためにメモリ ブロックを割り当てるに `operator delete` を使用するアロケーターを実装します。|  
|[allocator\_suballoc](../standard-library/allocator-suballoc-class.md)|型 [cache\_suballoc](../standard-library/cache-suballoc-class.md)のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。|  
|[allocator\_unbounded](../standard-library/allocator-unbounded-class.md)|[max\_unbounded](../standard-library/max-unbounded-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。|  
|[allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)|[max\_variable\_size](../standard-library/max-variable-size-class.md)によって管理される期間の型 [cache\_freelist](../standard-library/cache-freelist-class.md) のキャッシュを使用して型 `Type` オブジェクトの記憶割振エラーと解放を管理するオブジェクトを表します。|  
|[cache\_chunklist](../standard-library/cache-chunklist-class.md)|単一のサイズのメモリ ブロックの割り当てと解放するブロックのアロケーターを定義します。|  
|[cache\_freelist](../standard-library/cache-freelist-class.md)|単一のサイズのメモリ ブロックの割り当てと解放するブロックのアロケーターを定義します。|  
|[cache\_suballoc](../standard-library/cache-suballoc-class.md)|単一のサイズのメモリ ブロックの割り当てと解放するブロックのアロケーターを定義します。|  
|[freelist](../Topic/freelist%20Class.md)|メモリ ブロックのリストを管理します。|  
|[max\_fixed\_size](../standard-library/max-fixed-size-class.md)|最大クラス オブジェクトを制限する最大固定長に [freelist](../Topic/freelist%20Class.md) オブジェクトについて説明します。|  
|[max\_none](../Topic/max_none%20Class.md)|最大クラス オブジェクトをゼロに制限の最大長 [freelist](../Topic/freelist%20Class.md) オブジェクトについて説明します。|  
|[max\_unbounded](../standard-library/max-unbounded-class.md)|[freelist](../Topic/freelist%20Class.md) オブジェクトの最大長を制限する最大クラス オブジェクトを表します。|  
|[max\_variable\_size](../standard-library/max-variable-size-class.md)|最大クラス オブジェクトに制限を割り当てられたメモリ ブロック数に厳密に比例した最大長への [freelist](../Topic/freelist%20Class.md) オブジェクトについて説明します。|  
|[rts\_alloc](../standard-library/rts-alloc-class.md)|キャッシュ インスタンスの配列を保持する記述し、コンパイル時ではなく実行時に割り当ておよび解放として使用されるインスタンスを決定します rts\_alloc テンプレート クラスは [フィルター](../standard-library/allocators-header.md) を。|  
|[sync\_none](../standard-library/sync-none-class.md)|同期を行う同期フィルターについて説明します。|  
|[sync\_per\_container](../standard-library/sync-per-container-class.md)|各アロケーター オブジェクトには、別のキャッシュ オブジェクトを提供する同期フィルターについて説明します。|  
|[sync\_per\_thread](../standard-library/sync-per-thread-class.md)|スレッドごとに個別のキャッシュ オブジェクトを提供する同期フィルターについて説明します。|  
|[sync\_shared](../Topic/sync_shared%20Class.md)|すべてのアロケーターで共有されるキャッシュ オブジェクトへのアクセスを制御するミューテックスを使用して同期フィルターについて説明します。|  
  
## 必要条件  
 **ヘッダー:** の \<アロケーター\>  
  
 **名前空間:** stdext  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)