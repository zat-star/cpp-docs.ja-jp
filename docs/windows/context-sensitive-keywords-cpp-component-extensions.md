---
title: "状況依存のキーワード (C++ コンポーネント拡張) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "internal_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "状況依存のキーワード"
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 状況依存のキーワード (C++ コンポーネント拡張)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*状況依存のキーワード*は、特定のコンテキストでのみ認識される言語要素です。  特定のコンテキスト以外では、状況依存のキーワードをユーザー定義の記号として使用することができます。  
  
## すべてのランタイム  
 **解説**  
  
 以下は、状況依存のキーワードの一覧です。  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [イベント](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each、in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`\(「[メンバーの可視性](../Topic/Member%20Visibility.md)」を参照\)  
  
-   [literal](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [プロパティ](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` \([Generics](../windows/generics-cpp-component-extensions.md) の一部\)  
  
 読みやすくするために、状況依存のキーワードをユーザー定義の記号として使用することを制限することもできます。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 \(この機能のプラットフォーム固有の解説はありません。\)  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 \(この機能のプラットフォーム固有の解説はありません。\)  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次のコード例は、適切なコンテキストでは、`property` 状況依存キーワードを使用してプロパティと変数を定義できることを示しています。  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **出力**  
  
  **100**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)