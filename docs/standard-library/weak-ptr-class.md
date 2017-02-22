---
title: "weak_ptr クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.weak_ptr"
  - "tr1.weak_ptr"
  - "weak_ptr"
  - "tr1::weak_ptr"
  - "std::tr1::weak_ptr"
  - "memory/std::tr1::weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weak_ptr クラス"
  - "weak_ptr クラス [TR1]"
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# weak_ptr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関連付けの弱いポインターをラップします。  
  
## 構文  
  
```  
template<class Ty> class weak_ptr {  
public:  
    typedef Ty element_type;  
  
    weak_ptr();  
    weak_ptr(const weak_ptr&);  
    template<class Other>  
        weak_ptr(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr(const shared_ptr<Other>&);  
  
    weak_ptr& operator=(const weak_ptr&);  
    template<class Other>  
        weak_ptr& operator=(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr& operator=(shared_ptr<Other>&);  
  
    void swap(weak_ptr&);  
    void reset();  
  
    long use_count() const;  
    bool expired() const;  
    shared_ptr<Ty> lock() const;  
    };  
```  
  
#### パラメーター  
 `Ty`  
 ウィーク ポインターによって制御される型。  
  
## 解説  
 このテンプレート クラスは、1 つ以上の [shared\_ptr クラス](../standard-library/shared-ptr-class.md) クラス オブジェクトによって管理されるリソースを指し示すオブジェクトを表します。  リソースを指し示す `weak_ptr` オブジェクトは、そのリソースの参照カウントに一切影響を与えません。  したがって、リソースを管理する最後の `shared_ptr` オブジェクトが破棄されると、仮にそのリソースを指し示す `weak_ptr` オブジェクトが存在していたとしても、そのリソースは解放されます。  これは、データ構造の循環を防ぐうえで不可欠です。  
  
 `weak_ptr` オブジェクトは、リソースを所有する `shared_ptr` オブジェクトから構築された場合や、リソースを指し示す `weak_ptr` オブジェクトから構築された場合、またはリソースが [weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md) を使って割り当てられた場合に、そのリソースを指し示します。  `weak_ptr` オブジェクトから、そのオブジェクトが指し示すリソースに直接アクセスすることはできません。  そのリソースを使用する必要があるコードは、メンバー関数 [weak\_ptr::lock](../Topic/weak_ptr::lock.md) を呼び出すことによって作成された、そのリソースを所有する `shared_ptr` オブジェクトを介してそのリソースを使用します。  `weak_ptr` オブジェクトは、そのオブジェクトが指し示すリソースが解放されると、そのリソースを所有するすべての `shared_ptr` オブジェクトが破棄されるため、期限切れになります。  有効期限の切れた `weak_ptr` オブジェクトで `lock` を呼び出すと、空の shared\_ptr オブジェクトが作成されます。  
  
 空の weak\_ptr オブジェクトは、リソースを一切参照せず、コントロール ブロックも持ちません。  そのメンバー関数 `lock` は、空の shared\_ptr オブジェクトを返します。  
  
 循環は、`shared_ptr` オブジェクトによって制御される複数のリソースで、相互に参照し合う `shared_ptr` オブジェクトが保持されているときに発生します。  たとえば、3 つの要素から成るリンク リストがあるとします。先頭のノード `N0` が 2 番目のノード `N1` を所有する `shared_ptr` オブジェクトを保持し、2 番目のノードが 3 番目のノード `N2` を所有する `shared_ptr` オブジェクトを保持し、次に、3 番目のノードが先頭のノード `N0` を所有する `shared_ptr` オブジェクトを保持しているとすると、ループが閉じた状態になり、このリストは循環リンク リストになります。  この状況では、どの参照カウントもゼロにならないので、循環内のノードは解放されません。  この循環を解消するためには、最後のノード `N2` が、`shared_ptr` オブジェクトではなく、`N0` を指し示す `weak_ptr` オブジェクトを保持する必要があります。  `weak_ptr` オブジェクトは `N0` を所有しないので、`N0` の参照カウントに影響しません。先頭ノードに対するプログラムの最後の参照が破棄された時点で、リスト内のノードも破棄されます。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[weak\_ptr::weak\_ptr](../Topic/weak_ptr::weak_ptr.md)|`weak_ptr` を構築します。|  
  
### メソッド  
  
|||  
|-|-|  
|[weak\_ptr::element\_type](../Topic/weak_ptr::element_type.md)|要素の型。|  
|[weak\_ptr::expired](../Topic/weak_ptr::expired.md)|所有権の有効期限が切れているかどうかをテストします。|  
|[weak\_ptr::lock](../Topic/weak_ptr::lock.md)|リソースの排他的所有権を取得します。|  
|[weak\_ptr::owner\_before](../Topic/weak_ptr::owner_before.md)|この `weak_ptr` が、指定されたポインターの前 \(より小さい\) に順序付けされている場合は `true` を返します。|  
|[weak\_ptr::reset](../Topic/weak_ptr::reset.md)|所有されたリソースを解放します。|  
|[weak\_ptr::swap](../Topic/weak_ptr::swap.md)|2 つの `weak_ptr` オブジェクトを交換します。|  
|[weak\_ptr::use\_count](../Topic/weak_ptr::use_count.md)|指定された `shared_ptr` オブジェクトの数をカウントします。|  
  
### 演算子  
  
|||  
|-|-|  
|[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)|所有されたリソースを置換します。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [shared\_ptr クラス](../standard-library/shared-ptr-class.md)