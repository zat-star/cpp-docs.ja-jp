---
title: "コンパイラ エラー C3772 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 7bf4fc0d7e80d2bd77343ee43c31dc74b93c97de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3772"></a>コンパイラ エラー C3772
"name" : 無効なフレンド テンプレートの宣言  
  
クラス テンプレートの特殊化のフレンドを宣言することは無効です。 クラス テンプレートの明示的または部分的な特殊化を宣言し、同じステートメントでその特殊化のフレンドを宣言することはできません。 *name* プレースホルダーは、無効な宣言を識別します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   クラス テンプレートの特殊化のフレンドを宣言しません。  
  
-   アプリケーションに適切な場合は、クラス テンプレートのフレンドを宣言するか、特定の部分的または明示的な特殊化のフレンドを宣言します。  
  
## <a name="example"></a>例  
 次のコード例は、クラス テンプレートの部分的特殊化のフレンドを宣言しているため、失敗します。  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>関連項目  
[テンプレート](../../cpp/templates-cpp.md)   
[テンプレートの特殊化](../../cpp/template-specialization-cpp.md)   

