---
title: "コンパイラ エラー C3824 | Microsoft Docs"
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
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3824"
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー': この型は、このコンテキストには指定できません \(関数パラメーター、戻り値の型、または静的メンバー\)。  
  
 固定ポインターは、関数パラメーターまたは戻り値の型にしたり、`static` として宣言したりすることはできません。  
  
 次の例では警告 C3824 が生成されます。  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
  
 **C\+\+ マネージ拡張**  
  
 `__pin` キーワードで宣言されたローカル ポインターは、`static` として宣言できず、内部ポインターにできません。  
  
 次の例では警告 C3824 が生成されます。  
  
```  
// C3824b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc struct A {};  
  
void func() {  
   static A __pin* a;   // C3824  
   A __pin* b;   // OK  
}  
```