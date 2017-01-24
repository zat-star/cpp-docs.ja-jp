---
title: "function クラス | Microsoft Docs"
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
  - "functional/std::tr1::function"
  - "std.tr1.function"
  - "std::tr1::function"
  - "function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "function クラス [TR1]"
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

呼び出し可能オブジェクトのラッパーです。  
  
## 構文  
  
```cpp  
template<class Fty>  
   class function  // Fty of type Ret(T1, T2, ..., TN)  
   : public unary_function<T1, Ret>       // when Fty is Ret(T1)  
   : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)  
   {  
public:  
   typedef Ret result_type;  
  
   function();  
   function(nullptr_t);  
   function(const function& _Right);  
   template<class Fty2>  
      function(Fty2 fn);  
   template<class Fty2, class Alloc>  
       function (reference_wrapper<Fty2>, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       void assign (Fty2, const Alloc& _Ax);  
   template<class Fty2, class Alloc>  
       assign (reference_wrapper<Fty2>, const Alloc& _Ax);  
```  
  
```cpp  
function& operator=(nullptr_t);  
function& operator=(const function&);  
template<class Fty2>  
   function& operator=(Fty2);  
template<class Fty2>  
   function& operator=(reference_wrapper<Fty2>);  
void swap(function&);  
  
explicit operator bool() const;  
result_type operator()(T1, T2, ....., TN) const;  
  
const std::type_info& target_type() const;  
template<class Fty2>  
   Fty2 *target();  
template<class Fty2>  
   const Fty2 *target() const;  
```  
  
```cpp  
   template<class Fty2>  
      void operator==(const Fty2&) const = delete;  
   template<class Fty2>  
      void operator!=(const Fty2&) const = delete;  
};  
```  
  
#### パラメーター  
 `Fty`  
 ラップする関数の型。  
  
 `_Ax`  
 アロケーター関数。  
  
## 解説  
 このテンプレート クラスは、`Ret(T1, T2, ..., TN)` という呼び出しシグネチャを持つ呼び出しラッパーです。  さまざまな呼び出し可能オブジェクトを同一のラッパーで包むことができます。  
  
 一部のメンバー関数には、適切なターゲット オブジェクトをオペランドとして指定する必要があります。  その場合、オペランドは次のような方法で指定できます。  
  
 `fn` : 呼び出し可能オブジェクト `fn`。呼び出し後は、`function` オブジェクトが `fn` のコピーを保持します。  
  
 `fnref` : `fnref.get()` によって指定された呼び出し可能オブジェクト。呼び出し後は、`function` オブジェクトが `fnref.get()` への参照を保持します。  
  
 `right` : `function` オブジェクト `right` が保持する呼び出し可能オブジェクトとして \(存在する場合\)。  
  
 `npc` : null ポインター。呼び出し後は、`function` オブジェクトが空になります。  
  
 いずれの場合も、`INVOKE(f, t1, t2, ..., tN)` \(`f` は呼び出し可能オブジェクト、`t1, t2, ..., tN` はそれぞれ `T1, T2, ..., TN` 型の左辺値\) の形式が有効である必要があります。`Ret` が void 以外である場合は、`Ret` に変換可能であることが必要です。  
  
 空の `function` オブジェクトは、呼び出し可能オブジェクトも、呼び出し可能オブジェクトへの参照も保持しません。  
  
### コンストラクター  
  
|||  
|-|-|  
|[function::function](../Topic/function::function.md)|空のラッパを構築するか、固定シグネチャを持つ任意の型の呼び出し可能オブジェクトを格納します。|  
  
### Typedef  
  
|||  
|-|-|  
|[function::result\_type](../Topic/function::result_type.md)|格納されている呼び出し可能オブジェクトの戻り値の型です。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[function::assign](../Topic/function::assign.md)|この関数オブジェクトに、呼び出し可能オブジェクトを割り当てます。|  
|[function::swap](../Topic/function::swap.md)|2 つの呼び出し可能オブジェクトを交換します。|  
|[function::target](../Topic/function::target.md)|格納されている呼び出し可能オブジェクトが、指定されているように呼び出すことができるかどうかをテストします。|  
|[function::target\_type](../Topic/function::target_type.md)|呼び出し可能オブジェクトの型情報を取得します。|  
  
### 演算子  
  
|||  
|-|-|  
|[function::operator unspecified](../Topic/function::operator%20unspecified.md)|格納されている呼び出し可能オブジェクトが存在するかどうかをテストします。|  
|[function::operator\(\)](../Topic/function::operator\(\).md)|呼び出し可能オブジェクトを呼び出します。|  
|[function::operator\=](../Topic/function::operator=.md)|格納されている呼び出し可能オブジェクトを置き換えます。|  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [mem\_fn 関数](../Topic/mem_fn%20Function.md)   
 [reference\_wrapper クラス](../Topic/reference_wrapper%20Class.md)