---
title: "コンパイラ エラー C3253 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3253"
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 明示的なオーバーライドでエラーが発生しました  
  
 明示的なオーバーライドの指定が正しくありません。  たとえば、純粋オーバーライドとしても指定するオーバーライドの実装は指定できません。  詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3253 が生成されます。  
  
```  
// C3253.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
   void b();  
   void c();  
};  
  
public ref struct R : I {  
   virtual void a() = 0, I::a {}   // C3253  
   virtual void b() = I::a {}   // OK  
   virtual void c() = 0;   // OK  
};  
```