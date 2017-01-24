---
title: "コンパイラの警告 C4485 | Microsoft Docs"
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
  - "C4485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4485"
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function' : 基本 ref クラス メソッド 'base\_class\_function ' と一致しますが、'new' または 'override' に設定されていません。'new' \(および 'virtual'\) を仮定します  
  
 アクセサーは、`virtual` キーワードがあってもなくても基本クラス アクセサーをオーバーライドしますが、`override` 指定子または `new` 指定子が、オーバーライドする関数シグネチャに含まれていませんでした。  `new` 指定子または `override` 指定子を追加して、この警告を解決してください。  
  
 詳細については、「[override](../../windows/override-cpp-component-extensions.md)」および「[new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)」を参照してください。  
  
 C4485 は、常にエラーとして表示されます。  C4485 が表示されないようにするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
## 使用例  
 次の例では C4485 警告が生成されます。  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```