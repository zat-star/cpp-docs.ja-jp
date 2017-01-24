---
title: "override  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overriding, override keyword [C++]"
  - "override keyword [C++]"
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# override  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

状況依存の `override` キーワードは、型のメンバーが基底クラスまたは基本インターフェイスのメンバーをオーバーライドすることを示します。  
  
## 解説  
 `override` キーワードは、ネイティブ ターゲット \(既定のコンパイラ オプション\)、Windows ランタイム ターゲット \(**\/ZW** コンパイラ オプション\)、または共通言語ランタイム ターゲット \(**\/clr** コンパイラ オプション\) に対するコンパイル時に有効です。  
  
 オーバーライド指定子の詳細については、「[override 指定子](../cpp/override-specifier.md)」および「[Override Specifiers and Native Compilations \(オーバーライド指定子とネイティブ コンパイル\)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)」を参照してください。  
  
 状況依存のキーワードの詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
## 例  
 **例**  
  
 次のコード例に、`override` をネイティブ コンパイルでも使用できることを示します。  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **例**  
  
 次のコード例に、`override` を Windows ランタイム コンパイルで使用できることを示します。  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **要件**  
  
 コンパイラ オプション: **\/ZW**  
  
 **例**  
  
 次のコード例に、`override` を共通言語ランタイム コンパイルで使用できることを示します。  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **要件**  
  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [override 指定子](../cpp/override-specifier.md)   
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)