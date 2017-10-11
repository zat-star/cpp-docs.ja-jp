---
title: "オーバーライド指定子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 54c3b0de90ef3455af31c49592c6b405c345b0e9
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="override-specifier"></a>override 指定子
`override` キーワードを使用して、基底クラスの仮想関数をオーバーライドするメンバー関数を指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
function-declaration override;  
```  
  
## <a name="remarks"></a>コメント  
 `override` は状況依存のキーワードで、メンバー関数の宣言の後で使用した場合のみ特別な意味を持ちますが、それ以外の場合は、予約済みのキーワードではありません。  
  
## <a name="example"></a>例  
 `override` を使用すると、コード内での誤った継承動作を防止するのに役立ちます。 次の例では、`override` を使用しない場合に、派生クラスのメンバー関数で意図しない動作が発生する可能性があることを示します。 このコードに対してコンパイラ エラーは発生しません。  
  
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
  
 関数をオーバーライドできないことと、クラスの継承ができないことを指定するには、使用、[最終](../cpp/final-specifier.md)キーワード。  
  
## <a name="see-also"></a>関連項目  
 [final 指定子](../cpp/final-specifier.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 
