---
title: "override 指定子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "override 識別子"
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# override 指定子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`override` キーワードを使用して、基底クラスの仮想関数をオーバーライドするメンバー関数を指定できます。  
  
## 構文  
  
```  
  
function-declaration override;  
```  
  
## 解説  
 `override` は状況依存のキーワードで、メンバー関数の宣言の後で使用した場合のみ特別な意味を持ちますが、それ以外の場合は、予約済みのキーワードではありません。  
  
## 使用例  
 `override` を使用すると、コード内での誤った継承動作を防止するのに役立ちます。  次の例では、`override` を使用しない場合に、派生クラスのメンバー関数で意図しない動作が発生する可能性があることを示します。  このコードに対してコンパイラ エラーは発生しません。  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
  
};  
  
```  
  
 `override` を使用すると、コンパイラが自動的に新しいメンバー関数を作成するのではなく、エラーを生成するようになります。  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
  
```  
  
 関数のオーバーライドとクラスの継承の両方を無効にするには、[final](../cpp/final-specifier.md) キーワードを使用します。  
  
## 参照  
 [final 指定子](../cpp/final-specifier.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/ja-jp/b53ba470-e583-4e5c-b634-6018f6110674)