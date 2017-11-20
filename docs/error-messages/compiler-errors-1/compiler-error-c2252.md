---
title: "コンパイラ エラー C2252 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2252
dev_langs: C++
helpviewer_keywords: C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c390c4d72d2f9919a07087e71b687ac832521b11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2252"></a>コンパイラ エラー C2252
現在のスコープ内のテンプレートを明示的にインスタンス化できません。  
  
 テンプレートの明示的なインスタンス化に問題が検出されました。  たとえば、関数にテンプレートを明示的にインスタンス化できません。  
  
 次の例では、C2252 が生成されます。  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```