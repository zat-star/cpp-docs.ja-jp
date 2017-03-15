---
title: "コンパイラ エラー C3309 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3309"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3309"
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3309
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'macro\_name': モジュール名をマクロ、またはキーワードにすることはできません  
  
 モジュール属性の名前プロパティに渡す値を、展開するプリプロセッサのシンボルにすることはできません。文字列リテラルにする必要があります。  
  
 次の例では C3309 が生成されます。  
  
```  
// C3309.cpp #define NAME MyModule [module(name="NAME")];   // C3309 // Try the following line instead // [module(name="MyModule")]; [coclass] class MyClass { public: void MyFunc(); }; int main() { }  
```