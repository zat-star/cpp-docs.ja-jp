---
title: "コンパイラ エラー C3287 | Microsoft Docs"
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
  - "C3287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3287"
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型 'type' \(GetEnumerator の戻り値の型\) は、適切なパブリック MoveNext メンバー関数およびパブリック Current プロパティを含んでいなければなりません  
  
 ユーザー定義のコレクション クラスには、`MoveNext` と `Current` の定義を含める必要があります。  
  
 詳細については、「[方法: for each を使用してユーサー定義のコレクションを反復処理する](../Topic/How%20to:%20Iterate%20Over%20a%20User-Defined%20Collection%20with%20for%20each.md)」を参照してください。  
  
## 使用例  
 次の例では C3287 が生成されます。  
  
```  
// C3287.cpp // compile with: /clr using namespace System; ref struct R { bool MoveNext() { return true; } property Object^ Current { Object^ get() { Object ^ o = gcnew Object; return o; } } }; ref struct R2 { R ^GetEnumerator() { R^ r = gcnew R; return r; } }; ref struct T {}; ref struct T2 { T ^GetEnumerator() { T^ t = gcnew T; return t; } }; int main() { for each (int i in gcnew T2) {}   // C3287 for each (int i in gcnew R2) {}   // OK }  
```