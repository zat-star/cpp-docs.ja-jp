---
title: "final 指定子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "final"
  - "final_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "final 識別子"
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# final 指定子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`final` キーワードを使用して、派生クラスでオーバーライドできない仮想関数を指定できます。  また、このキーワードは、継承できないクラスの指定にも使用できます。  
  
## 構文  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## 解説  
 `final` は状況依存のキーワードで、関数宣言またはクラス名の後で使用した場合にのみ特別な意味を持ちますが、それ以外の場合は予約済みのキーワードではありません。  
  
 `final` をクラス宣言内で使用した場合、その宣言の `base-classes` の部分は省略可能になります。  
  
## 使用例  
 次の例では、`final` キーワードを使用して、仮想関数をオーバーライドできないことを指定しています。  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 メンバー関数をオーバーライドできることを指定する方法については、「[override 指定子](../cpp/override-specifier.md)」を参照してください。  
  
 次の例では、`final` キーワードを使用して、クラスが継承できないことを指定しています。  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/ja-jp/b53ba470-e583-4e5c-b634-6018f6110674)   
 [override 指定子](../cpp/override-specifier.md)