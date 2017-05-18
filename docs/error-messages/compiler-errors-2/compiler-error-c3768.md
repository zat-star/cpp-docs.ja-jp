---
title: "コンパイラ エラー C3768 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: cb9c1c3a41deb35e6aa82d3d77e61dfd4b15a7cb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3768"></a>コンパイラ エラー C3768
仮想 vararg 関数のアドレスを純粋マネージ コードで指定できません  
  
 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 コンパイルすると`/clr:pure`、仮想のアドレスを受け取ることはできません`vararg`関数です。  
  
## <a name="example"></a>例  

 次の例では、c3768 エラーが生成されます。  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```
