---
title: "左辺値参照宣言子: &amp; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&'
dev_langs:
- C++
helpviewer_keywords:
- reference operator
- '& operator, reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
caps.latest.revision: 14
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
ms.openlocfilehash: 6aa0c0a18d77f685369681c0d0400ada6f879e9d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="lvalue-reference-declarator-amp"></a>左辺値参照宣言子:&amp;
オブジェクトのアドレスを保持しますが、オブジェクトのように構文的に実行されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
type-id & cast-expression  
```  
  
## <a name="remarks"></a>コメント  
 lvalue 参照は、オブジェクトの別名と考えることができます。 左辺値参照の宣言は、参照宣言子が続く指定子のオプションのリストから構成されます。 参照は初期化する必要があり、変更できません。  
  
 アドレスを特定のポインター型に変換できるオブジェクトは、類似した参照型にも変換できます。 たとえば、アドレスを `char *` 型に変換できるオブジェクトは、`char &` 型にも変換できます。  
  
 使用した参照の宣言を混同しないでください、 [address-of 演算子](../cpp/address-of-operator-amp.md)です。 ときに、 `&`*識別子*は後に、型など`int`または`char`、*識別子*型への参照として宣言されています。 ときに`&`*識別子*前がない使用法では、型によっては、address-of 演算子のです。  
  
## <a name="example"></a>例  
 次の例は、`Person` オブジェクトの宣言による参照宣言子と、そのオブジェクトへの参照を示します。 `rFriend` は `myFriend` への参照であるため、いずれかの変数を更新すると同じオブジェクトが変更されます。  
  
```  
// reference_declarator.cpp  
// compile with: /EHsc  
// Demonstrates the reference declarator.  
#include <iostream>  
using namespace std;  
  
struct Person  
{  
    char* Name;  
    short Age;  
};  
  
int main()  
{  
   // Declare a Person object.  
   Person myFriend;  
  
   // Declare a reference to the Person object.  
   Person& rFriend = myFriend;  
  
   // Set the fields of the Person object.  
   // Updating either variable changes the same object.  
   myFriend.Name = "Bill";  
   rFriend.Age = 40;  
  
   // Print the fields of the Person object to the console.  
   cout << rFriend.Name << " is " << myFriend.Age << endl;  
}  
```  
  
```Output  
Bill is 40  
```  
  
## <a name="see-also"></a>関連項目  
 [参照](../cpp/references-cpp.md)   
 [参照型関数の引数](../cpp/reference-type-function-arguments.md)   
 [参照型関数の戻り値](../cpp/reference-type-function-returns.md)   
 [ポインターへの参照](../cpp/references-to-pointers.md)
