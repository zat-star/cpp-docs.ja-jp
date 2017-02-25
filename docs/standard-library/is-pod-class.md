---
title: "is_pod クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_pod"
  - "is_pod"
  - "std::tr1::is_pod"
  - "std.is_pod"
  - "std::is_pod"
  - "type_traits/std::is_pod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pod クラス [TR1]"
  - "is_pod"
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# is_pod クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が POD かどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_pod;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が POD \(Plain Old Data\) である場合、`is_pod<Ty>::value` は `true` です。  それ以外の場合は `false` です。  
  
 演算型、列挙型、ポインター型、およびメンバーへのポインター型は、POD です。  
  
 POD 型の cv\-qualified バージョンは、それ自体が POD 型です。  
  
 POD の配列は、それ自体が POD です。  
  
 すべての非静的データ メンバーが POD である構造体または共用体は、次に該当する場合、それ自体が POD です。  
  
-   ユーザーが宣言したコンストラクターを持たない。  
  
-   非静的なプライベートまたはプロテクト データ メンバーを持たない。  
  
-   基底クラスを持たない。  
  
-   仮想関数を持たない。  
  
-   参照型の非静的データ メンバーを持たない。  
  
-   ユーザー定義のコピー代入演算子を持たない。  
  
-   ユーザー定義のデストラクターを持たない。  
  
 したがって、POD 型の構造体や配列を含む POD 型の構造体や配列を再帰的に構築できます。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct throws   
    {   
    throws() throw(int)   
        {   
        }   
  
    throws(const throws&) throw(int)   
        {   
        }   
  
    throws& operator=(const throws&) throw(int)   
        {   
        }   
  
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pod\<trivial\> \=\= true**  
**is\_pod\<int\> \=\= true**  
**is\_pod\<throws\> \=\= false**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)