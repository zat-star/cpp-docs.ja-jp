---
title: "方法: interface 静的コンストラクターを定義する (C++/CLI) | Microsoft Docs"
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
  - "コンストラクター [C++]"
  - "interface 静的コンストラクター"
  - "静的コンストラクター, interface"
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: interface 静的コンストラクターを定義する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスは、静的データ メンバーを初期化するために使用できる静的コンストラクターを持つことができます。静的コンストラクターは、静的なインターフェイス メンバーに最初にアクセスしたときに、一度に最大で呼び出され、前に呼び出されます。  
  
 静的コンストラクターの詳細については、「[方法: クラスまたは構造体の静的コンストラクターを定義する](../misc/how-to-define-static-constructors-in-a-class-or-struct.md)」を参照してください。  
  
## 使用例  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
  **MyInterface の静的コンストラクター**  
**99**  
**99**  
**99**   
## 参照  
 [interface class](../windows/interface-class-cpp-component-extensions.md)