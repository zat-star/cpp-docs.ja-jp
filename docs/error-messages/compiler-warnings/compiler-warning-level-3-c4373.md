---
title: "コンパイラの警告 (レベル 3) C4373 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 36d4491f8a621f1ee97de9682faf94a26a89fa70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4373"></a>コンパイラの警告 (レベル 3) C4373
'%$S': 仮想関数は '%$pS' をオーバーライドします。前バージョンのコンパイラは、パラメーターの違いが const/volatile 修飾子に限られる場合はオーバーライドしませんでした。  
  
 アプリケーションには、基底クラス仮想メソッドをオーバーライドする派生クラスでメソッドが含まれ、オーバーライドするメソッドのパラメーターが異なるだけ、 [const](../../cpp/const-cpp.md)または[揮発性](../../cpp/volatile-cpp.md)仮想メソッドのパラメーターから修飾子。 つまり、コンパイラでは、基底クラスまたは派生クラスのいずれかにおけるメソッドに、関数参照をバインドする必要があります。  
  
 バージョンより前のバージョンのコンパイラの[!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)]基底クラス内のメソッドに関数をバインドし、警告メッセージを発行します。 それ以降のバージョンのコンパイラでは、 `const` または `volatile` の修飾子を無視して、派生クラスのメソッドに関数をバインドした後、警告 `C4373`を発行します。 この後者の動作は、C++ 標準に準拠しています。  
  
## <a name="example"></a>例  
 次のコード例では、警告 C4373 が生成されます。  
  
```  
// c4373.cpp  
// compile with: /c /W3  
#include <stdio.h>  
struct Base  
{  
    virtual void f(int i) {  
        printf("base\n");  
    }  
};  
struct Derived : Base  
{  
    void f(const int i) {  // C4373  
        printf("derived\n");  
    }  
};  
void main()  
{  
    Derived d;  
    Base* p = &d;  
    p->f(1);  
}  
```  
  
```Output  
derived  
```
