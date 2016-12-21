---
title: "コンパイラ エラー C3391 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3391"
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg' : ジェネリック 'generic\_type' のジェネリック パラメーター 'param' の型引数が正しくありません。Null 非許容の値型でなければなりません  
  
 ジェネリック型のインスタンス化が正しく行われませんでした。  型定義を確認してください。  詳細については、次のトピックを参照してください。<xref:System.Nullable> および[Generics](../../windows/generics-cpp-component-extensions.md).  
  
## 使用例  
 次の例では、C\# を使用してジェネリック型を含むコンポーネントを作成していますが、[!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)] でジェネリック型を作成するときにはサポートされない特定の制約があります。 詳細については、「[型パラメーターの制約](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)」をご覧ください。  
  
```  
// C3391.cs // compile with: /target:library // a C# program public class GR<N> where N : struct {}  
```  
  
## 使用例  
 次の例では C3391 が生成されます。  
  
```  
// C3391_b.cpp // compile with: /clr #using <C3391.dll> using namespace System; value class VClass {}; int main() { GR< Nullable<VClass> >^ a = gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable GR<VClass>^ aa = gcnew GR<VClass>();   // OK }  
```