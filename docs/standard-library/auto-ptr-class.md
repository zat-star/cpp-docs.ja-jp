---
title: "auto_ptr クラス | Microsoft Docs"
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
  - "std::auto_ptr"
  - "std.auto_ptr"
  - "auto_ptr"
  - "memory/std::auto_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_ptr クラス"
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# auto_ptr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールがあるブロックを離れるときに確実にリソースが自動的に破棄されるように、リソースの周囲にスマート ポインターをラップします。  
  
 より高機能なこの `unique_ptr` クラスは `auto_ptr` に代わるものです。  詳細については、「[unique\_ptr クラス](../standard-library/unique-ptr-class.md)」をご覧ください。  
  
 `throw()` および例外処理の詳細については、「[例外の仕様 \(スロー\)](../cpp/exception-specifications-throw-cpp.md)」をご覧ください。  
  
## 構文  
  
```  
template<class Type>  
    class auto_ptr {  
public:  
    typedef Type element_type;  
    explicit auto_ptr(Type *_Ptr = 0) throw();  
    auto_ptr(auto_ptr<Type>& _Right) throw();  
    template<class Other>  
        operator auto_ptr<Other>() throw();  
    template<class Other>  
        auto_ptr<Type>& operator=(auto_ptr<Other>& _Right) throw();  
    template<class Other>  
        auto_ptr(auto_ptr<Other>& _Right);  
    auto_ptr<Type>& operator=(auto_ptr<Type>& _Right);  
    ~auto_ptr();  
    Type& operator*() const throw();  
    Type *operator->()const throw();  
    Type *get() const throw();  
    Type *release()throw();  
    void reset(Type *_Ptr = 0);  
};  
```  
  
#### パラメーター  
 `_Right`  
 既存のリソースの取得元となる `auto_ptr`。  
  
 `_Ptr`  
 格納されたポインターを置換するように指定されたポインター。  
  
## 解説  
 このテンプレート クラスは、割り当てられたオブジェクトを指し示す `auto_ptr,` と呼ばれるスマート ポインターを記述します。  このポインターは、null であるか、`new` によって割り当てられたオブジェクトを指定する必要があります。  `auto_ptr` は、格納されている値が別のオブジェクトに割り当てられている場合、所有権を転送します。  \(転送後、格納されている値は null ポインターに置換されます。\) `auto_ptr<Type>` のデストラクターが割り当てられたオブジェクトを削除します。  `auto_ptr<Type>` は、コントロールがブロックを離れるとき、例外がスローされる場合であっても、割り当てられたオブジェクトが確実に自動的に削除するようにします。  同じオブジェクトを所有する 2 つの `auto_ptr<Type>` オブジェクトを構成しないでください。  
  
 `auto_ptr<Type>` オブジェクトを関数呼び出しの引数として値渡しで渡せます。  `auto_ptr` を標準ライブラリのコンテナーの要素にすることはできません。  標準テンプレート ライブラリのコンテナーを持つ `auto_ptr<Type>` オブジェクトのシーケンスを確実に管理することはできません。  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[auto\_ptr](../Topic/auto_ptr::auto_ptr.md)|`auto_ptr` 型のオブジェクトのコンストラクター。|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/auto_ptr::element_type.md)|この型は、テンプレート パラメーター `Type` の同意語です。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[取得](../Topic/auto_ptr::get.md)|このメンバー関数は、格納されているポインター `myptr` を返します。|  
|[リリース](../Topic/auto_ptr::release.md)|このメンバーは、格納されたポインター `myptr` を null ポインターで置換して、以前に格納されたポインターを返します。|  
|[リセット](../Topic/auto_ptr::reset.md)|このメンバー関数は、関数呼び出しの結果として格納されているポインター値 `myptr` が変化する場合に限り、式 `delete myptr` を評価します。  その後、格納されたポインターを `ptr` で置換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/auto_ptr::operator=.md)|1 つの `auto_ptr` オブジェクトから別のオブジェクトに所有権を転送する代入演算子。|  
|[operator\*](../Topic/auto_ptr::operator*.md)|`auto_ptr` 型のオブジェクトの逆参照演算子。|  
|[operator\-\>](../Topic/auto_ptr::operator-%3E.md)|メンバーにアクセスできるようにする演算子。|  
|[operator auto\_ptr\<Other\>](../Topic/auto_ptr::operator%20auto_ptr%3COther%3E.md)|1 つの種類の `auto_ptr` から別の種類の `auto_ptr` にキャストします。|  
|[operator auto\_ptr\_ref\<Other\>](../Topic/auto_ptr::operator%20auto_ptr_ref%3COther%3E.md)|`auto_ptr` から `auto_ptr_ref` にキャストします。|  
  
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique\_ptr クラス](../standard-library/unique-ptr-class.md)