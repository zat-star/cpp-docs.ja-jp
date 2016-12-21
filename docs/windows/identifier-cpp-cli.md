---
title: "__identifier (C++/CLI) | Microsoft Docs"
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
  - "__identifier"
  - "__identifier_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__identifier keyword [C++]"
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __identifier (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

識別子として Visual C\+\+ キーワードを使用できます。  
  
## すべてのプラットフォーム  
 **構文**  
  
```  
  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
 **解説**  
  
 キーワードでない識別子の `__identifier` キーワードの使用は許可されますが、厳密なので、スタイルの関係しないでください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
### 例  
 **例**  
  
 次の例では、`template` というクラスを C\# で作成され、DLL として配布されます。  `template` クラスを使用する Visual C\+\+ プログラムでは、`__identifier` キーワードは `template` は標準 C\+\+ キーワードであるという事実を非表示にします。  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 `__identifier` キーワードは **\/clr** と **\/clr:oldSyntax** のコンパイラ オプションで有効です。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 次の例では、`template` というクラスを C\# で作成され、DLL として配布されます。  `template` クラスを使用する Visual C\+\+ プログラムでは、`__identifier` キーワードは `template` は標準 C\+\+ キーワードであるという事実を非表示にします。  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)