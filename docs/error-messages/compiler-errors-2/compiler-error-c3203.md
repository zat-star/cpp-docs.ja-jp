---
title: "コンパイラ エラー C3203 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3203
dev_langs: C++
helpviewer_keywords: C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe6f908cb4ba507f113ec838813cbb10d228fabd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3203"></a>コンパイラ エラー C3203
'type': 非特殊クラス テンプレートまたはジェネリックは、テンプレートまたはジェネリック引数としてテンプレートまたはジェネリック パラメーター 'param' に使用できません。実際の型を指定してください  
  
 無効な引数をクラス テンプレートまたはジェネリックに渡しました。 クラス テンプレートまたはジェネリックには、パラメーターとして型を渡す必要があります。  
  
 このエラーは、Visual C++ 2005 のために行われたコンパイラ準拠作業の結果として生成される場合があります。非特殊クラス テンプレートは、基底クラス リストのテンプレート引数として使用できません。 C3203 を解決するには、基底クラス リストでテンプレート パラメーターとしてテンプレート型パラメーターを使用するときに、明示的にテンプレート型パラメーターをテンプレート クラス名に追加します。  
  
```  
// C3203.cpp  
template< typename T >  
struct X {  
   void f(X) {}  
};  
  
template< typename T >  
struct Y : public X<Y> {   // C3203  
// try the following line instead  
// struct Y : public X<Y<T> > {  
   void f(Y) {}  
};  
  
int main() {  
   Y<int> y;  
}  
```  
  
 次の例は C3203 を生成し、その修正方法を示しています。  
  
```  
// C3203_b.cpp  
// compile with: /c  
template <class T>  
struct S1 {};  
  
template <class T>  
class C1 {};  
  
typedef C1<S1> MyC1;   // C3203  
  
// OK  
template <template <class> class T>  
class C2 {};  
  
typedef C2<S1> MyC1;  
  
template <class T>  
class C3 {};  
  
typedef C3<S1<int> > MyC12;  
```  
  
 C3203 は、ジェネリックを使用しているときも発生します。  
  
```  
// C3203_c.cpp  
// compile with: /clr /c  
generic <class T>  
value struct GS1 {};  
  
generic <class T>  
value struct GC1 {};  
  
typedef GC1<GS1> MyGC1;   // C3203  
typedef GC1<GS1<int> > MyGC2;   // OK  
```