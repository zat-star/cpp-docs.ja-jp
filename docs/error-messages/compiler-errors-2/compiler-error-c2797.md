---
title: "コンパイラ エラー C2797 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 5eea0aae37627015f8723835e4e3e1cb0c6d2e94
ms.contentlocale: ja-jp
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2797"></a>コンパイラ エラー C2797
(廃止)メンバー初期化子リストまたは非静的データ メンバー初期化子の内部リストの初期化は実装されていません。  
  
 この警告は、Visual Studio 2015 で廃止されています。 Visual Studio 2013 以前のバージョンでは、Visual C コンパイラは、メンバー初期化子リストまたは非静的データ メンバー初期化子のいずれかの内部リスト初期化機能を実装していません。 Visual Studio 2013 Update 3 より前は、これはサイレントに関数呼び出しに変換され、これにより、不適切なコードが生成される可能性がありました。 Visual Studio 2013 Update 3 ではこのことがエラーとして報告されます。  
  
 この例では、C2797 が生成されます。  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 また、この例では C2797 も生成されます。  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 この問題を解決するには、内部リストの明示的な構築を使用できます。 次に例を示します。  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 リストの初期化が必要ない場合:  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 (Visual Studio 2013 Update 3 より前は、Visual Studio 2013 の コンパイラによって暗黙的にこのことが行われました。)
