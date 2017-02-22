---
title: "コンパイラ エラー C3392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3392"
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg' : ジェネリック パラメーター 'param' \(ジェネリック 'generic\_type'\) の型引数が無効です。パブリックのパラメーターのないコンストラクターを含んでいなければなりません  
  
 ジェネリック型のインスタンス化が正しく行われませんでした。  型定義をご確認ください。  詳しくは、「[Generics](../../windows/generics-cpp-component-extensions.md)」をご覧ください。  
  
## 使用例  
 次の例では、C\# を使用してジェネリック型を含むコンポーネントを作成していますが、[!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)] でジェネリック型を作成するときにはサポートされない特定の制約があります。 詳しくは、「[型パラメーターの制約](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)」をご覧ください。  
  
```  
// C3392.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## 使用例  
 次の例では C3392 が生成されます。  
  
```  
// C3392_b.cpp // compile with: /clr #using <C3392.dll> ref class R { R(int) {} }; ref class N { N() {} }; value class V {}; ref class N2 { public: N2() {} }; ref class R2 { public: R2() {} }; int main () { GR<R^, V, N^>^ gr1;   // C3392 GR<R^, V, N2^>^ gr1a;   // OK GR<R^, N^, N^>^ gr3;   // C3392 GR<R^, V, N2^>^ gr3a;   // OK GR<R^, V, R^>^ gr4;   // C3392 GR<R^, V, R2^>^ gr4a;   // OK }  
```