---
title: "コンパイラ エラー C3648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3648"
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この明示的なオーバーライド構文には \/clr:oldSyntax が必要です  
  
 最新のマネージ構文のコンパイル時に、以前のバージョンの明示的なオーバーライド構文が見つかりました。  
  
 詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  以前のバージョンの構文の詳細については、「[明示的なオーバーライド](../../cpp/explicit-overrides-cpp.md)」を参照してください。  
  
 次の例では警告 C3648 が生成されます。  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```