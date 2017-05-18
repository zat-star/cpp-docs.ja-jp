---
title: "コンパイラ エラー C3390 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 257b0678ded15815f6673091d1adb26dea1dec12
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3390"></a>コンパイラ エラー C3390
'type_arg' : ジェネリック 'generic_type' のジェネリック パラメーター 'param' の型引数が無効です。参照型でなければなりません  
  
ジェネリック型のインスタンス化が正しく行われませんでした。  型定義をご確認ください。  詳細については、次を参照してください。[ジェネリック](../../windows/generics-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
C + でのジェネリック型を作成するときにサポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する最初のサンプルを使用して c#/cli CLR です。 詳細については、次を参照してください。[型パラメーターの制約](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters)します。  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
C3390.dll コンポーネントが利用できる場合、次の例には、c3390 エラーが生成されます。  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```
