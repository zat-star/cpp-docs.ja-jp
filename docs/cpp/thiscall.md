---
title: "__thiscall | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__thiscall"
  - "__thiscall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__thiscall キーワード [C++]"
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __thiscall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__thiscall` 呼び出し規約はメンバー関数で使用され、可変個引数を使用しない C\+\+ メンバー関数によって使用される既定の呼び出し規約です。  `__thiscall` では呼び出し先がスタックをクリーンアップしますが、これは `vararg` 関数では不可能です。  引数は、x86 アーキテクチャでは、スタックではなくレジスタ ECX を介して渡される `this` ポインターでスタックに右から左へプッシュされます。  
  
 `__thiscall` を使用する理由の 1 つは、メンバー関数が `__clrcall` を既定で使用するクラスにあります。  その場合、`__thiscall` を使用して、個々のメンバー関数をネイティブ コードから呼び出すことができます。  
  
 [\/clr:pure](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルすると、すべての関数および関数ポインターは、特に指定がない場合は `__clrcall` になります。  
  
 Visual C\+\+ 2005 以前のリリースでは、`thiscall` がキーワードではないため、thiscall 呼び出し規約を明示的に指定できませんでした。  
  
 `vararg` メンバー関数は `__cdecl` の呼び出し規約を使用します。  関数のすべての引数は、スタックにプッシュされ、`this` ポインターが最後にスタックに配置されます。  
  
 この呼び出し規約は C\+\+ だけに適用されるため、C の名前の装飾スキームはありません。  
  
 ARM および [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンピューターでは、`__thiscall` がコンパイラによって受け入れられたり、無視されたりします。  
  
 静的でないクラスの関数が行外で宣言されている場合、行外の宣言で呼び出し規約の修飾子を指定する必要はありません。  つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。  
  
## 使用例  
  
```  
// thiscall_cc.cpp  
// compile with: /c /clr:oldSyntax  
struct CMyClass {  
   void __thiscall mymethod();  
   void __clrcall mymethod2();  
};  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [引数の渡し規則と名前付け規則](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)