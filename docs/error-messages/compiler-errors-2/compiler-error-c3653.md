---
title: "コンパイラ エラー C3653 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3653"
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 名前付きオーバーライドとして使用できません: オーバーライドされる関数が見つかりません。:: 演算子を使用して明示的に関数の名前を指定してください  
  
 明示的なオーバーライドで、インターフェイスにない関数が指定されました。  詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3653 が生成されます。  
  
```  
// C3653.cpp  
// compile with: /clr  
public interface struct I {  
   void h();  
};  
  
public ref struct X : public I {  
   virtual void f() new sealed = J {};   // C3653 no J in scope  
   virtual void g() {}   // OK  
   virtual void h() new sealed = I::h {};   // OK  
};  
```