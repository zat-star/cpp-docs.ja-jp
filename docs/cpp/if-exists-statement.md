---
title: "__if_exists ステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_exists_cpp"
  - "__if_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_exists キーワード [C++]"
  - "識別子, テスト (存在するかどうかを)"
  - "シンボル, テスト (存在するかどうかを)"
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __if_exists ステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__if_exists` ステートメントは、指定された識別子があるかどうかをテストします。  ID が存在する場合、指定されたステートメント ブロックが実行されます。  
  
## 構文  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`identifier`|存在をテストしたい識別子。|  
|`statements`|`identifier`  が存在する場合に実行する 1 つ以上のステートメント。|  
  
## 解説  
  
> [!CAUTION]
>  最も信頼できる結果を得るには、次の制約に基づいて `__if_exists` ステートメントを使用します。  
  
-   テンプレートではなく、単純型にのみ `__if_exists` ステートメントを適用します。  
  
-   クラスの内部または外部の識別子に `__if_exists` ステートメントを適用します。  ローカル変数に `__if_exists` ステートメントを適用しないでください。  
  
-   `__if_exists` ステートメントは関数の本体でのみ使用します。  関数本体の外側では、`__if_exists` ステートメントは完全に定義された型のみテストできます。  
  
-   オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。  
  
 [\_\_if\_not\_exists](../cpp/if-not-exists-statement.md) ステートメントは、`__if_exists` ステートメントを補完します。  
  
## 使用例  
 この例ではテンプレートを使用していますが、これは推奨されません。  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## 出力  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## 参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\_\_if\_not\_exists ステートメント](../cpp/if-not-exists-statement.md)