---
title: "メンバー関数テンプレート | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数テンプレート, メンバー関数"
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メンバー関数テンプレート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

用語メンバー テンプレートは、メンバー関数テンプレートと入れ子になったクラス テンプレートを示します。  メンバー関数テンプレートは、クラスまたはクラス テンプレートのメンバーであるテンプレート関数です。  詳細については、「[入れ子のクラス テンプレート](../Topic/Nested%20Class%20Templates.md)」を参照してください。  
  
 メンバー関数は複数のコンテキストの関数テンプレートになります。  クラス テンプレートのすべての関数はジェネリックですが、メンバー テンプレートまたはメンバー関数テンプレートとしては参照されません。  これらのメンバー関数が独自のテンプレート引数を受け取る場合、それらの関数はメンバー関数テンプレートと見なされます。  詳細については、「[テンプレート クラスのメンバー関数](../Topic/Member%20Functions%20of%20Template%20Classes.md)」を参照してください。  
  
## 使用例  
 非テンプレート クラスまたはテンプレート クラスのメンバー関数テンプレートは、テンプレート パラメーターを持つ関数テンプレートとして宣言されます。  
  
```  
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## 使用例  
 次の例は、テンプレート クラスのメンバー関数テンプレートを示します。  
  
```  
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## 使用例  
 また、Visual Studio .NET 2003 以降では、メンバー テンプレートもクラスの外部で定義できます。  
  
```  
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## 使用例  
 ローカル クラスはメンバー テンプレートを持つことができません。  
  
 メンバー テンプレート関数は、仮想関数にできません。また、基底クラスの仮想関数と同じ名前で宣言されている場合に、基底クラスから仮想関数をオーバーライドできません。  
  
 Visual C\+\+ .NET 2003 では、テンプレート化されたユーザー定義変換のサポートが導入されました。  次のサンプルは、Visual C\+\+ .NET 2003 で標準の仕様のとおりに動作します。  
  
```  
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## 参照  
 [関数テンプレート](../cpp/function-templates.md)