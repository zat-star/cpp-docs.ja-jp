---
title: "コンパイラ エラー C3225 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4cf62ba7b0c3b95f22c27172546ccdd253ed9279
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3225"></a>コンパイラ エラー C3225
'arg' のジェネリック型引数は 'type' をすることはできません、値型であるまたはハンドル型にする必要があります。  
  
 ジェネリック型引数は、適切な型でした。  
  
 詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 ネイティブ型を持つジェネリック型をインスタンス化することはできません。 次の例では、C3225 を生成します。  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## <a name="example"></a>例  
 次の例では、c# を使用してコンポーネントを作成します。 制約では、ジェネリック型が値型でインスタンス化できますのみ指定されることを確認します。  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>例  
 このサンプルを使用して c# でコンポーネントを作成して MyList のみが有効な制約に違反する以外の値の型でインスタンス化される<xref:System.Nullable>です。 次の例では、C3225 を生成します。  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```
