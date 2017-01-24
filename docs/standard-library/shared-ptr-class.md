---
title: "shared_ptr クラス | Microsoft Docs"
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
  - "shared_ptr"
  - "tr1::shared_ptr"
  - "memory/std::tr1::shared_ptr"
  - "std::tr1::shared_ptr"
  - "std.tr1.shared_ptr"
  - "tr1.shared_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared_ptr クラス"
  - "shared_ptr クラス [TR1]"
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
caps.latest.revision: 29
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shared_ptr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照カウント スマート ポインターを、動的に割り当てられたオブジェクトにラップします。  
  
## 構文  
  
```  
template<class Ty>  
   class shared_ptr {  
public:  
    typedef Ty element_type;  
  
    shared_ptr();  
    shared_ptr(nullptr_t);   
    shared_ptr(const shared_ptr& sp);  
    shared_ptr(shared_ptr&& sp);  
    template<class Other>  
        explicit shared_ptr(Other * ptr);  
    template<class Other, class D>  
        shared_ptr(Other * ptr, D dtor);  
    template<class D>  
        shared_ptr(nullptr_t, D dtor);  
    template<class Other, class D, class A>  
        shared_ptr(Other *ptr, D dtor, A alloc);  
    template<class D, class A>  
        shared_ptr(nullptr_t, D dtor, A alloc);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>&& sp);  
    template<class Other>  
        explicit shared_ptr(const weak_ptr<Other>& wp);  
    template<class Other>  
        shared_ptr(auto_ptr<Other>& ap);  
    template<class Other, class D>  
        shared_ptr(unique_ptr<Other, D>&& up);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp, Ty *ptr);  
    ~shared_ptr();  
    shared_ptr& operator=(const shared_ptr& sp);  
    template<class Other>   
        shared_ptr& operator=(const shared_ptr<Other>& sp);  
    shared_ptr& operator=(shared_ptr&& sp);  
    template<class Other>   
        shared_ptr& operator=(shared_ptr<Other>&& sp);  
    template<class Other>   
        shared_ptr& operator=(auto_ptr< Other >&& ap);  
    template <class Other, class D>   
        shared_ptr& operator=(const unique_ptr< Other, D>& up) = delete;  
    template <class Other, class D>  
        shared_ptr& operator=(unique_ptr<Other, D>&& up);  
    void swap(shared_ptr& sp);  
    void reset();  
    template<class Other>  
        void reset(Other *ptr);  
    template<class Other, class D>  
        void reset(Other *ptr, D dtor);  
    template<class Other, class D, class A>  
        void reset(Other *ptr, D dtor, A alloc);  
    Ty *get() const;  
    Ty& operator*() const;  
    Ty *operator->() const;  
    long use_count() const;  
    bool unique() const;  
    operator bool() const;  
  
    template<class Other>  
        bool owner_before(shared_ptr<Other> const& ptr) const;  
    template<class Other>  
        bool owner_before(weak_ptr<Other> const& ptr) const;  
    template<class D, class Ty>   
        D* get_deleter(shared_ptr<Ty> const& ptr);  
};  
  
```  
  
#### パラメーター  
 `Ty`  
 共有ポインターによって制御される型。  
  
 `Other`  
 引数ポインターによって制御される型。  
  
 `ptr`  
 コピーするポインター。  
  
 `D`  
 削除子の型。  
  
 `A`  
 アロケーターの型。  
  
 `dtor`  
 削除子。  
  
 `alloc`  
 アロケーター。  
  
 `sp`  
 コピーまたは移動するスマート ポインター。  
  
 `wp`  
 コピーまたは移動するウィーク ポインター。  
  
 `ap`  
 コピーまたは移動する自動ポインター。  
  
 `up`  
 移動する一意のポインター。  
  
## 解説  
 このテンプレート クラスは、参照カウントを使ってリソースを管理するオブジェクトを表します。  `shared_ptr` オブジェクトは、所有しているリソースへのポインターまたは null ポインターを効率的に保持します。  複数の `shared_ptr` オブジェクトが 1 つのリソースを所有することもできます。その場合、特定のリソースを所有する最後の `shared_ptr` オブジェクトが破棄された時点で、リソースが解放されます。  
  
 `shared_ptr` は、再割り当てまたはリセットされるとリソースの所有を停止します。  
  
 テンプレートの引数 `Ty` は、特定のメンバー関数について注記がある場合を除き、不完全な型になる場合があります。  
  
 `shared_ptr<Ty>` オブジェクトを `G*` 型のリソース ポインターまたは `shared_ptr<G>` から構築する場合、ポインターの型 `G*` は `Ty*` に変換可能であることが必要です。  この条件が満たされていない場合、コードはコンパイルされません。  例:  
  
```cpp  
class F {};  
class G : public F {};  
```  
  
```cpp  
  
#include <memory>  
  
using namespace std;  
  
shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*  
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>  
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*  
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>  
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>  
shared_ptr<int> sp5(new G); // error, G* not convertible to int*  
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>  
```  
  
 `shared_ptr` オブジェクトがリソースを所有するためには、次のいずれかの条件を満たしている必要があります。  
  
-   そのリソースへのポインターを使って構築されている。  
  
-   そのリソースを所有する `shared_ptr` オブジェクトから構築されている。  
  
-   そのリソースを指し示す [weak\_ptr クラス](../standard-library/weak-ptr-class.md) オブジェクトから構築されている。  
  
-   そのリソースの所有権が、[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md) またはメンバー関数 [shared\_ptr::reset](../Topic/shared_ptr::reset.md) の呼び出しのいずれかによって割り当てられている。  
  
 リソースを所有する `shared_ptr` オブジェクトは、コントロール ブロックを共有します。  コントロール ブロックは以下の情報を保持します。  
  
-   リソースを所有する `shared_ptr` オブジェクトの数。  
  
-   リソースを指す `weak_ptr` オブジェクトの数。  
  
-   リソースの削除子 \(存在する場合\)  
  
-   コントロール ブロックのカスタム アロケーター \(存在する場合\)  
  
 null ポインターを使用して初期化される `shared_ptr` オブジェクトにはコントロール ブロックが存在し、空ではありません。  `shared_ptr` オブジェクトがリソースを所有するのは、そのリソースが解放されるまでの間です。  `weak_ptr` オブジェクトがリソースを指しているのは、そのリソースが解放されるまでの間です。  
  
 リソースを所有する `shared_ptr` オブジェクトの数がゼロになると、リソースを削除するか、リソースのアドレスを削除子に渡すことによって、リソースが解放されます。どちらの方法で解放されるかは、最初にリソースの所有権が作成された方法によって決定されます。  リソースを所有する `shared_ptr` オブジェクトの数がゼロになり、そのリソースを指す `weak_ptr` オブジェクトの数がゼロになると、コントロール ブロックのカスタム アロケーターを使用して \(存在する場合\)、コントロール ブロックが解放されます。  
  
 空の `shared_ptr` オブジェクトは、リソースを一切所有せず、コントロール ブロックも持ちません。  
  
 削除子は、メンバー関数 `operator()` を持つ関数オブジェクトです。  この型はコピーによって構築可能であること、また、コピー コンストラクターおよびデストラクターによって例外がスローされないことが必要です。  削除子は、削除するオブジェクトを指定する 1 つのパラメーターを受け入れます。  
  
 一部の関数では、結果として生成される `shared_ptr<Ty>` または `weak_ptr<Ty>` オブジェクトのプロパティを定義する引数リストが使用されます。  その場合、引数リストは次のような方法で指定できます。  
  
 引数なし: 結果として生成されるオブジェクトは、空の `shared_ptr` オブジェクトまたは空の `weak_ptr` オブジェクトです。  
  
 `ptr` \-\- 管理対象リソースへの `Other*` 型のポインター。  `Ty` は完全な型である必要があります。  コントロール ブロックを割り当てることができないため関数が失敗した場合、`delete ptr` という式が評価されます。  
  
 `ptr, dtor`: 管理対象リソースに対する `Other*` 型のポインターおよびそのリソースの削除子です。  コントロール ブロックを割り当てることができなかったことが原因で関数が失敗した場合、`dtor(ptr)` が呼び出されます \(明確に定義されていることが必要\)。  
  
 `ptr, dtor, alloc` \-\- 管理対象リソース、そのリソースの削除子、および割り当てと解放を行う必要があるすべてのストレージを管理するためのアロケーターへの `Other*` 型のポインター。  コントロール ブロックを割り当てることができなかったことが原因で関数が失敗した場合、`dtor(ptr)` が呼び出されます \(明確に定義されていることが必要\)。  
  
 `sp`: 管理対象のリソースを所有する `shared_ptr<Other>` オブジェクトです。  
  
 `wp`: 管理対象のリソースを指し示す `weak_ptr<Other>` オブジェクトです。  
  
 `ap`: 管理対象のリソースへのポインターを保持する `auto_ptr<Other>` オブジェクトです。  関数が成功した場合は、`ap.release()` が呼び出されます。関数が失敗した場合は、`ap` は変更されません。  
  
 いずれの場合も、ポインターの型 `Other*` は `Ty*` に変換可能である必要があります。  
  
## スレッド セーフ  
 複数のスレッドが異なる `shared_ptr` オブジェクト \(所有権を共有するコピーである場合も含めて\) に対する読み取りと書き込みを同時に行うことができます。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[shared\_ptr::shared\_ptr](../Topic/shared_ptr::shared_ptr.md)|`shared_ptr` を構築します。|  
|[shared\_ptr::~shared\_ptr](../Topic/shared_ptr::~shared_ptr.md)|`shared_ptr` を破棄します。|  
  
### メソッド  
  
|||  
|-|-|  
|[shared\_ptr::element\_type](../Topic/shared_ptr::element_type.md)|要素の型。|  
|[shared\_ptr::get](../Topic/shared_ptr::get.md)|所有されているリソースのアドレスを取得します。|  
|[shared\_ptr::owner\_before](../Topic/shared_ptr::owner_before.md)|この `shared_ptr` が、指定されたポインターの前に順序付けされている \(またはそれよりも少ない\) 場合は true を返します。|  
|[shared\_ptr::reset](../Topic/shared_ptr::reset.md)|所有されたリソースを置き換えます。|  
|[shared\_ptr::swap](../Topic/shared_ptr::swap.md)|2 つの `shared_ptr` オブジェクトを交換します。|  
|[shared\_ptr::unique](../Topic/shared_ptr::unique.md)|所有されたリソースが一意であるかどうかをテストします。|  
|[shared\_ptr::use\_count](../Topic/shared_ptr::use_count.md)|リソース所有者の数をカウントします。|  
  
### 演算子  
  
|||  
|-|-|  
|[shared\_ptr::operator boolean\-type](../Topic/shared_ptr::operator%20boolean-type.md)|所有されたリソースが存在するかどうかをテストします。|  
|[shared\_ptr::operator\*](../Topic/shared_ptr::operator*.md)|指定された値を取得します。|  
|[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)|所有されたリソースを置き換えます。|  
|[shared\_ptr::operator\-\>](../Topic/shared_ptr::operator-%3E.md)|指定された値へのポインターを取得します。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [weak\_ptr クラス](../standard-library/weak-ptr-class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)