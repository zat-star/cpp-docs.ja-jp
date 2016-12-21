---
title: "方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オーバーライド指定子 (ネイティブ コンパイルの)、オーバーライド"
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ネイティブ コンパイルでオーバーライド指定子を宣言する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[sealed](../windows/sealed-cpp-component-extensions.md)、[抽象](../windows/abstract-cpp-component-extensions.md)と [オーバーライド](../windows/override-cpp-component-extensions.md) は **\/ZW** または [\/clr](../build/reference/clr-common-language-runtime-compilation.md)を使用しないでコンパイルで使用できます。  
  
> [!NOTE]
>  ISO の標準 C\+\+11 言語に [オーバーライド](../cpp/override-specifier.md) の ID と [最後](../cpp/final-specifier.md) 識別子があり、両方のネイティブのみようにコンパイルしてよいコードの `sealed` ではなく、Visual Studio を使用 `final` でサポートされます。  
  
## 例  
  
### 説明  
 次の例では `sealed` がネイティブ コンパイルで有効であることを示します。  
  
### コード  
  
```  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## 例  
  
### 説明  
 `override` がネイティブ コンパイルで有効であることを次の例に示します。  
  
### コード  
  
```  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## 例  
  
### 説明  
 この例では `abstract` がネイティブ コンパイルで有効であることを示します。  
  
### コード  
  
```  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## 参照  
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)