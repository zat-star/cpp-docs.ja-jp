---
title: "メンバー関数の概要 | Microsoft Docs"
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
  - "インライン関数, メンバー関数の取り扱い"
  - "メンバー関数, クラス宣言内での定義"
  - "非静的メンバー関数"
  - "このポインター, および非静的メンバー関数"
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# メンバー関数の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メンバー関数は静的か非静的のいずれかになります。  静的メンバー関数は暗黙の **this** 引数を持たないため、静的メンバー関数の動作は他のメンバー関数とは異なります。  非静的なメンバー関数には **this** ポインターがあります。  メンバー関数は、静的であるないにかかわらず、クラス宣言の内外に定義できます。  
  
 メンバー関数がクラス宣言の中で定義されている場合、インライン関数として扱われ、そのクラス名で関数名を修飾する必要はありません。  クラス宣言内部で定義される関数はインライン関数として既に処理されますが、**inline** キーワードを使用してコードを記述できます。  
  
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
  
 メンバー関数の定義がクラス宣言外である場合、その関数は、**inline** として明示的に宣言されている場合にのみインライン関数として扱われます。  また、定義内の関数名はスコープ解決演算子 \(`::`\) を使用してクラス名で修飾する必要があります。  
  
 次の例は、`Deposit` 関数がクラス宣言の外側で定義されていることを除き、クラス `Account` の以前の宣言と同じです。  
  
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
  
 メンバー関数を含むクラスは多くの宣言を持つことができますが、メンバー関数自体は 1 つのプログラムに定義を 1 つのみ持つ必要があります。  複数の定義により、リンク時にエラー メッセージが発生します。  クラスにインライン関数定義が含まれている場合、この "1 つの定義" 規則に従うために、関数定義は同じにする必要があります。  
  
## 参照  
 [メンバー関数](../Topic/Member%20Functions%20\(C++\).md)