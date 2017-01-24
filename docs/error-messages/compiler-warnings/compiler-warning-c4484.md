---
title: "コンパイラの警告 C4484 | Microsoft Docs"
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
  - "C4484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4484"
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function' : 基本 ref クラス メソッド 'base\_class\_function ' と一致しますが、'virtual'、'new' または 'override' に設定されていません。'new' \(および 'virtual' でない\) を仮定します  
  
 **\/clr** を指定してコンパイルすると、基本クラス関数は暗黙にオーバーライドされません。つまり、関数は vtable の新しいスロットを取得します。  これを解決するには、関数をオーバーライドするかどうかを明示的に指定します。  
  
 詳細については、次のトピックを参照してください。  
  
-   [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 は、常にエラーとして表示されます。  C4484 が表示されないようにするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
## 使用例  
 次の例では C4484 エラーが生成されます。  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```