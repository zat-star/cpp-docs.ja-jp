---
title: "コンパイラ エラー C3391 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3391
dev_langs: C++
helpviewer_keywords: C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8501d0a645d656bd0c86f093d1591985f9a3499a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3391"></a>コンパイラ エラー C3391
'type_arg': ジェネリック パラメーター 'param' のジェネリック 'generic_type' の無効な型引数が null 非許容値型にする必要があります  
  
ジェネリック型のインスタンス化が正しく行われませんでした。 型定義を確認してください。 詳細については、次を参照してください。<xref:System.Nullable>と[ジェネリック](../../windows/generics-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
C + におけるジェネリック型を作成するときにサポートされていない特定の制約を持つジェネリック型を含むコンポーネントを作成する C# の場合、次のサンプルを使用して + CLI です。 詳細については、「[型パラメーターの制約](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)」を参照してください。  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
C3391.dll コンポーネントが利用できる場合、次の例には C3391 が生成されます。  
  
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