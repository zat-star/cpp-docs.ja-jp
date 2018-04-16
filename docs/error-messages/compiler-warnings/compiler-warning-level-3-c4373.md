---
title: "コンパイラの警告 (レベル 3) C4373 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43523cb5f4c024ec3e937e88fca7f78c341ab19d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4373"></a>コンパイラの警告 (レベル 3) C4373
'%$S': 仮想関数は '%$pS' をオーバーライドします。前バージョンのコンパイラは、パラメーターの違いが const/volatile 修飾子に限られる場合はオーバーライドしませんでした。  
  
 アプリケーションには、基底クラスの仮想メソッドをオーバーライドする派生クラスのメソッドが含まれ、オーバーライドする側のメソッドのパラメーターは、 [const](../../cpp/const-cpp.md) または [volatile](../../cpp/volatile-cpp.md) 修飾子についてのみ、仮想メソッドのパラメーターと異なります。 つまり、コンパイラでは、基底クラスまたは派生クラスのいずれかにおけるメソッドに、関数参照をバインドする必要があります。  
  
 [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] より前のバージョンのコンパイラでは、基底クラスのメソッドに関数をバインドした後、警告メッセージを発行します。 それ以降のバージョンのコンパイラでは、 `const` または `volatile` の修飾子を無視して、派生クラスのメソッドに関数をバインドした後、警告 `C4373`を発行します。 この後者の動作は、C++ 標準に準拠しています。  
  
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