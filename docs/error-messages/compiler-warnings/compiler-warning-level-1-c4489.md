---
title: "コンパイラの警告 (レベル 1) C4489 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4489"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4489"
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラの警告 (レベル 1) C4489
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'指定子' : インターフェイス メソッド 'メソッド' では使用できません。オーバーライド指定子は、ref クラスおよび値クラス メソッドでのみ使用できます  
  
 指定子のキーワードが、インターフェイス メソッドで正しく使用されていません。  
  
 詳細については、「[オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4489 エラーが生成されます。  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```