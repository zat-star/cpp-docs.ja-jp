---
title: "/Gd、/Gr、/Gv、/Gz (呼び出し規約) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gr"
  - "/Gv"
  - "/gz"
  - "/Gd"
  - "VC.Project.VCCLCompilerTool.CallingConvention"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gd コンパイラ オプション [C++]"
  - "/Gr コンパイラ オプション [C++]"
  - "/Gv コンパイラ オプション [C++]"
  - "/Gz コンパイラ オプション [C++]"
  - "Gd コンパイラ オプション [C++]"
  - "-Gd コンパイラ オプション [C++]"
  - "Gr コンパイラ オプション [C++]"
  - "-Gr コンパイラ オプション [C++]"
  - "Gv コンパイラ オプション [C++]"
  - "-Gv コンパイラ オプション [C++]"
  - "Gz コンパイラ オプション [C++]"
  - "-Gz コンパイラ オプション [C++]"
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gd、/Gr、/Gv、/Gz (呼び出し規約)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのオプションでは、関数の引数をスタックにプッシュする順序、呼び出し元と呼び出し先のどちらの関数が呼び出しの最後にスタックから引数を削除するか、および個々の関数を識別するためにコンパイラが使用する名前装飾規約を決定します。  
  
## 構文  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## 解説  
 **\/Gd** は、[\_\_stdcall](../../cpp/stdcall.md)、[\_\_fastcall](../../cpp/fastcall.md)、または [\_\_vectorcall](../Topic/__vectorcall.md) が指定されている関数と C\+\+ メンバー関数を除く、すべての関数の [\_\_cdecl](../Topic/__cdecl.md) 呼び出し規約を指定します。これは既定の設定です。  
  
 **\/Gr** は、`__fastcall` 呼び出し規約を指定します。ただし、C\+\+ メンバー関数、`main` という名前の関数、および `__cdecl`、`__stdcall`、または `__vectorcall` が指定されている関数に対しては指定できません。  すべての `__fastcall` 関数には、プロトタイプ宣言が必要です。  この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。  
  
 **\/Gz** は、`__stdcall` 呼び出し規約を指定します。ただし、C\+\+ メンバー関数、`main` という名前の関数、および `__cdecl`、`__fastcall`、または `__vectorcall` が指定されている関数に対しては指定できません。  すべての `__stdcall` 関数には、プロトタイプ宣言が必要です。  この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。  
  
 **\/Gv** は `__vectorcall` 呼び出し規約を指定します。ただし、C\+\+ メンバー関数、main という名前の関数、可変個引数リスト `vararg` を使用する関数、競合する属性 `__cdecl`、`__stdcall`、または  `__fastcall` が指定されている関数に対しては指定できません。  この呼び出し規約は、\/arch:SSE2 以上をサポートする x86 アーキテクチャおよび x64 アーキテクチャのみで使用され、ARM アーキテクチャを対象とするコンパイラでは無視されます。  
  
 可変数の引数を受け取る関数には `__cdecl` が指定されている必要があります。  
  
 **\/Gd**、**\/Gr**、**\/Gv** および **\/Gz** は、[\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) または **\/clr:pure** と互換性がありません。  
  
> [!NOTE]
>  既定では、x86 プロセッサの場合、C\+\+ メンバー関数は [\_\_thiscall](../../cpp/thiscall.md) を使用します。  
  
 すべてのプロセッサで、`__cdecl`、`__fastcall`、`__vectorcall`、または `__stdcall` のいずれかとして明示的に指定されているメンバー関数では、指定の呼び出し規約が使用されます \(そのアーキテクチャで無視されない場合\)。  可変個の引数を取るメンバー関数では、常に `__cdecl` 呼び出し規約が使われます。  
  
 これのコンパイラ オプションを指定しても、C\+\+ のメソッドや関数の名前装飾規約には影響しません。  `extern "C"` として宣言しない限り、C\+\+ のメソッドや関数では、別の名前装飾規約が使用されます。  詳細については、「[装飾名](../Topic/Decorated%20Names.md)」を参照してください。  
  
 呼び出し規約の詳細については、「[呼び出し規約](../Topic/Calling%20Conventions.md)」を参照してください。  
  
## \_\_cdecl の場合  
 x86 プロセッサでは、すべての関数の引数は、スタックで右から左へ渡されます。  ARM アーキテクチャおよび x64 アーキテクチャでは、一部の引数はレジスタで渡され、残りの引数はスタックで右から左へ渡されます。  呼び出しルーチンによって、スタックから引数がポップされます。  
  
 C の `__cdecl` 名前付け規則では、関数名の前にアンダースコア \(`_`\) が付けられ、大文字小文字は変換されません。  `extern "C"` として宣言しない限り、C\+\+ の関数では、別の名前装飾規約が使用されます。  詳細については、「[装飾名](../Topic/Decorated%20Names.md)」を参照してください。  
  
## \_\_fastcall の場合  
 `__fastcall` 関数の一部の引数はレジスタ \(x86 プロセッサの場合 ECX および EDX\) で渡され、その他の引数は右から左の順にスタックにプッシュされます。  これらの引数は、呼び出し元に制御が戻る前に、呼び出し先のルーチンによってスタックからポップされます。  通常、**\/Gr** オプションを使用すると実行速度が上がります。  
  
> [!NOTE]
>  インライン アセンブリ言語で記述された関数に対して `__fastcall` 呼び出し規約を使用する場合は注意してください。  レジスタを使用すると、コンパイラ側で使用するレジスタと競合する場合があります。  
  
 C の `__fastcall` 名前付け規則では、関数名の前にアット マーク \(`@`\) を付け、その後ろに関数の引数の大きさをバイト数で示します。  大文字と小文字は変換されません。  コンパイラでは、次の名前付け規則用テンプレートが使用されます。  
  
```c  
@function_name@number  
```  
  
 `__fastcall` 名前付け規則を使う場合は、標準のインクルード ファイルを使用してください。  使用しないと、外部参照が解決されません。  
  
## \_\_stdcall の場合  
 `__stdcall` 関数の引数は、右から左の順序でスタックにプッシュされます。これらの引数は、呼び出し元に制御が戻る前に、呼び出し先の関数によってポップされます。  
  
 C の `__stdcall` 名前付け規則では、関数名の前にアンダースコア \(`_`\) を付け、関数名の最後にアット マーク \(@\) を付けます。このアット マーク \(@\) の後ろに、関数の引数の大きさをバイト数で示します。  大文字小文字は変換されません。  コンパイラでは、次の名前付け規則用テンプレートが使用されます。  
  
```c  
_functionname@number  
```  
  
## \_\_vectorcall の場合  
 `__vectorcall` 関数の整数引数は、最大 2 個 \(x86\) または最大 4 個 \(x64\) の整数レジスタ、および浮動小数点とベクター値の場合は最大の 6 個の XMM レジスタを使用して値渡しされ、その他はスタックで右から左へ渡されます。  呼び出された関数は、制御を戻す前にスタックをクリーンオフします。  ベクターと浮動小数点戻り値は、XMM0 で返されます。  
  
 C の `__vectorcall` 名前付け規則では、関数名の後ろに 2 つのアット マーク \(@@\) を付け、その後ろに関数の引数の大きさをバイト数で示します。  大文字小文字は変換されません。  コンパイラでは、次の名前付け規則用テンプレートが使用されます。  
  
```c  
functionname@@number  
```  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box.  For details, see [方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md).  
  
2.  Select the **C\/C\+\+** folder.  
  
3.  Select the **Advanced** property page.  
  
4.  Modify the **Calling Convention** property.  
  
### To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)