---
title: "コンパイラ エラー C2752 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2752
dev_langs: C++
helpviewer_keywords: C2752
ms.assetid: ae42b3ec-84a9-4e9d-8d59-3d208132d0b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9ec3809b4826cf336391e561839840af44593cb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2752"></a>コンパイラ エラー C2752
'template': 2 つ以上の部分的特殊化がテンプレート引数リストと一致します。  
  
 インスタンス化があいまいです。  
  
 次の例では、C2752 が生成されます。  
  
```  
// C2752.cpp  
template<class T, class U>   
struct A {};  
  
template<class T, class U>   
struct A<T*, U> {};  
  
template<class T, class U>   
struct A<T,U*> {};  
  
// try the following line instead  
// template<class T, class U> struct A<T*,U*> {};  
  
int main() {  
   A<char*,int*> a;   // C2752 an instantiation  
  
   // OK  
   A<char*,int> a1;  
   A<char,int*> a2;  
   A<char,int> a3;  
}  
```