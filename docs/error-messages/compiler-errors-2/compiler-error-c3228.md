---
title: "コンパイラ エラー C3228 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3228
dev_langs: C++
helpviewer_keywords: C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1176da0e3c2583d5a48d78a9f2689d5cf0bc40be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3228"></a>コンパイラ エラー C3228
'function' : 'param' のジェネリック型引数を 'type' にすることはできません。値型またはハンドル型にする必要があります  
  
 正しくない型がジェネリック型引数として渡されました。  
  
 次の例では C3228 が生成されます。  
  
```  
// C3228.cpp  
// compile with: /clr  
class A {};  
  
value class B {};  
  
generic <class T>  
void Test() {}  
  
ref class C {  
public:  
   generic <class T>  
   static void f() {}  
};  
  
int main() {  
   C::f<A>();   // C3228  
   C::f<B>();   // OK  
  
   Test<C>();   // C3228  
   Test<C ^>();   // OK  
}  
```