---
title: "コンパイラ エラー C3665 | Microsoft Docs"
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
  - "C3665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3665"
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'デコンストラクター' : オーバーライド指定子 'キーワード' は 'デコンストラクター\/ファイナライザー' では使用できません  
  
 デストラクターまたはファイナライザーでは使用できないキーワードが使用されています。  
  
 たとえば、new スロットは、デストラクターまたはファイナライザーでは要求できません。詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」と「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  
  
 次の例では警告 C3665 が生成されます。  
  
```  
// C3665.cpp  
// compile with: /clr  
public ref struct R {  
   virtual ~R() { }  
   virtual void a() { }  
};  
  
public ref struct S : R {  
   virtual ~S() new {}   // C3665  
   virtual void a() new {}   // OK  
};  
```