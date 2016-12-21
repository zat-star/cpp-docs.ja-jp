---
title: "コンパイラ エラー C3490 | Microsoft Docs"
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
  - "C3490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3490"
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' は const オブジェクトを通じてアクセスされているため変更できません  
  
 `const` メソッドで宣言されているラムダ式は、変更不能なメンバー データを変更することはできません。  
  
### このエラーを解決するには  
  
-   メソッド宣言から `const` 修飾子を削除します。  
  
## 使用例  
 次の例では、`const` メソッドでメンバー変数 `_i` を変更するため、C3490 が生成されます。  
  
```  
// C3490a.cpp // compile with: /c class C { void f() const  { auto x = [=]() { _i = 20; }; // C3490 } int _i; };  
```  
  
## 使用例  
 次の例では、メソッド宣言から `const` 修飾子を削除して C3490 を解決します。  
  
```  
// C3490b.cpp // compile with: /c class C { void f() { auto x = [=]() { _i = 20; }; } int _i; };  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)