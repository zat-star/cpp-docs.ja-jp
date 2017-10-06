---
title: "メンバー関数の概要 |Microsoft ドキュメント"
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
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: cc73317962c92a7f35d103b342ca52aa0bef4f2e
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="overview-of-member-functions"></a>メンバー関数の概要
メンバー関数は静的か非静的のいずれかになります。 静的メンバー関数の動作は、静的メンバー関数は暗黙ために、他のメンバー関数とは異なります。**この**引数。 非静的メンバー関数が、**この**ポインター。 メンバー関数は、静的であるないにかかわらず、クラス宣言の内外に定義できます。  
  
 メンバー関数がクラス宣言の中で定義されている場合、インライン関数として扱われ、そのクラス名で関数名を修飾する必要はありません。 クラス宣言内で定義された関数はインライン関数として扱われます、使用すると、**インライン**コードを説明するキーワードです。  
  
 クラス宣言内で関数を宣言する例を示します。  
  
```  
// overview_of_member_functions1.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit within the declaration  
    //  of class Account.  
    double Deposit( double HowMuch )  
    {  
        balance += HowMuch;  
        return balance;  
    }  
private:  
    double balance;  
};  
  
int main()  
{  
}  
```  
  
 として明示的に宣言されている場合にのみ、メンバー関数の定義がクラス宣言の外側にある場合は、そのはインライン関数として扱わ**インライン**です。 また、定義内の関数名はスコープ解決演算子 (`::`) を使用してクラス名で修飾する必要があります。  
  
 次の例は、`Account` 関数がクラス宣言の外側で定義されていることを除き、クラス `Deposit` の以前の宣言と同じです。  
  
```  
// overview_of_member_functions2.cpp  
class Account  
{  
public:  
    // Declare the member function Deposit but do not define it.  
    double Deposit( double HowMuch );  
private:  
    double balance;  
};  
  
inline double Account::Deposit( double HowMuch )  
{  
    balance += HowMuch;  
    return balance;  
}  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  メンバー関数がクラス宣言の内部でも個別でも定義できますが、メンバー関数は、クラスが定義された後でクラスに追加することはできません。  
  
 メンバー関数を含むクラスは多くの宣言を持つことができますが、メンバー関数自体は 1 つのプログラムに定義を 1 つのみ持つ必要があります。 複数の定義により、リンク時にエラー メッセージが発生します。 クラスにインライン関数定義が含まれている場合、この "1 つの定義" 規則に従うために、関数定義は同じにする必要があります。  
  

