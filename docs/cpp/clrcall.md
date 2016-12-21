---
title: "__clrcall | Microsoft Docs"
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
  - "__clrcall"
  - "__clrcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__clrcall キーワード [C++]"
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __clrcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 関数がマネージ コードからのみ呼び出されることを指定します。  マネージ コードからのみ呼び出されるすべての仮想関数では `__clrcall` を使用します。  ただし、この呼び出し規約は、ネイティブ コードから呼び出される関数には使用できません。  
  
 マネージ関数から仮想マネージ関数を呼び出す場合、またはマネージ関数からポインターを使用してマネージ関数を呼び出す場合は、`__clrcall` を使用してパフォーマンスを向上させます。  
  
 エントリ ポイントはコンパイラが生成した個別の関数です。  関数にネイティブ エントリ ポイントとマネージ エントリ ポイントがある場合、そのいずれかが、関数実装を持つ実際の関数になります。  もう一方の関数は実際の関数に呼び出す別の関数 \(サンク\) で、共通言語ランタイムに PInvoke を実行させます。  関数を `__clrcall` としてマークすると、関数の実装が MSIL である必要があり、ネイティブ エントリ ポイント関数が生成されないことを示します。  
  
 `__clrcall` が指定されていない場合にネイティブ関数のアドレスを取得すると、コンパイラはネイティブ エントリ ポイントを使用します。  `__clrcall` は、関数が管理され、マネージ コードからネイティブへの遷移を行う必要がないことを示します。  その場合、コンパイラはマネージ エントリ ポイントを使用します。  
  
 **\/clr** を使用し \(**\/clr:pure** または **\/clr:safe** ではなく\)、`__clrcall` を使用しない場合は、関数のアドレスを取得すると常にネイティブ エントリ ポイント関数のアドレスが返ります。  `__clrcall` を使用すると、ネイティブ エントリ ポイント関数が作成されないため、エントリ ポイント サンク関数ではなくマネージ関数のアドレスを取得します。  詳細については、「[ダブル サンキング](../Topic/Double%20Thunking%20\(C++\).md)」を参照してください。  
  
 [\/clr \(共通言語ランタイムのコンパイル\)](../build/reference/clr-common-language-runtime-compilation.md) は、すべての関数および関数ポインターが `__clrcall` であり、コンパイラがコンパイル単位内の関数が `__clrcall` 以外にマークされることを許可しないことを意味します。  **\/clr:pure** を使用するときは、`__clrcall` は関数ポインターと外部宣言でのみ指定できます。  
  
 この関数が MSIL を実装している限り、**\/clr** を使用してコンパイルされた既存の C\+\+ コードから `__clrcall` 関数を直接呼び出すことができます。  `__clrcall` 関数は、インライン asm を持ち CPU 固有の組み込み関数を呼び出す関数から直接呼び出すことはできません。たとえば、それらの関数が **\/clr** でコンパイルされている場合でも直接呼び出すことはできません。  
  
 `__clrcall` 関数ポインターだけが、作成されたアプリケーション ドメインで使用されるようになっています。  アプリケーション ドメインを越えて `__clrcall` 関数ポインターを渡すのではなく、<xref:System.CrossAppDomainDelegate> を使用します。  詳細については、「[アプリケーション ドメインと Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md)」を参照してください。  
  
## 使用例  
  
```  
// clrcall.cpp  
// compile with: /clr:oldSyntax /LD  
void __clrcall Test1( ) {}  
void (__clrcall *fpTest1)( ) = &Test1;  
```  
  
## 使用例  
 関数が `__clrcall` で宣言されている場合、必要に応じて \(関数が呼び出された場合など\) コードが生成されることに注意してください。  
  
```  
// clrcall2.cpp  
// compile with: /clr  
using namespace System;  
int __clrcall Func1() {  
   Console::WriteLine("in Func1");  
   return 0;  
}  
  
// Func1 hasn't been used at this point (code has not been generated),   
// so runtime returns the adddress of a stub to the function  
int (__clrcall *pf)() = &Func1;  
  
// code calls the function, code generated at difference address  
int i = pf();   // comment this line and comparison will pass  
  
int main() {  
   if (&Func1 == pf)  
      Console::WriteLine("&Func1 == pf, comparison succeeds");  
   else   
      Console::WriteLine("&Func1 != pf, comparison fails");  
  
   // even though comparison fails, stub and function call are correct  
   pf();  
   Func1();  
}  
```  
  
  **in Func1**  
**&Func1 \!\= pf, comparison fails**  
**in Func1**  
**in Func1**   
## 使用例  
 次のサンプルでは、関数ポインターが管理されたコードからのみ呼び出されるように、関数ポインターを定義する方法を示します。  これにより、コンパイラはマネージ関数を直接呼び出し、ネイティブ エントリ ポイント \(ダブル サンクの問題\) を避けることができます。  
  
```  
// clrcall3.cpp  
// compile with: /clr  
void Test() {  
   System::Console::WriteLine("in Test");  
}  
  
int main() {  
   void (*pTest)() = &Test;  
   (*pTest)();  
  
   void (__clrcall *pTest2)() = &Test;  
   (*pTest2)();  
}  
```  
  
## 参照  
 [引数の渡し規則と名前付け規則](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)