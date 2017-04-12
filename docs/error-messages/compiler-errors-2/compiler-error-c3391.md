---
title: "コンパイラ エラー C3391 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
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
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 7b5922ccf353162dc32c99e3818227639d0f5985
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3391"></a>コンパイラ エラー C3391
'type_arg': ジェネリック パラメーター ジェネリック 'generic_type' の ' param' に無効な型引数は、null 非許容値型である必要があります  
  
ジェネリック型のインスタンス化が正しく行われませんでした。 型定義をご確認ください。 詳細については、次を参照してください<xref:System.Nullable>と[ジェネリック](../../windows/generics-cpp-component-extensions.md)。</xref:System.Nullable> 。  
  
## <a name="example"></a>例  
C + でのジェネリック型を作成するときにサポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する次の例を使用して c#/cli CLI です。 詳細については、次を参照してください。[型パラメーターの制約](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters)します。  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
C3391.dll コンポーネントが利用できる場合、次の例には、c3391 エラーが生成されます。  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```
