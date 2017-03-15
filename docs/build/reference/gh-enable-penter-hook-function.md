---
title: "/Gh (_penter フック関数の有効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_penter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh コンパイラ オプション [C++]"
  - "_penter 関数"
  - "Gh コンパイラ オプション [C++]"
  - "-Gh コンパイラ オプション [C++]"
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Gh (_penter フック関数の有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべてのメソッドまたは関数の先頭で `_penter` 関数を呼び出します。  
  
## 構文  
  
```  
/Gh  
```  
  
## 解説  
 `_penter` 関数はライブラリ関数ではなく、`_penter` の定義はユーザー自身が行います。  
  
 `_penter` 関数のプロトタイプを宣言する必要があるのは、\_penter 関数を明示的に呼び出す場合だけです。  この関数は、次に示すプロトタイプがあらかじめ宣言されているものとして記述します。この関数では、呼び出し元から制御が渡された時点ですべてのレジスタの内容をプッシュし、呼び出し元に制御を返す時点でそれをポップして元の状況に戻す必要があります。  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 この宣言は、64 ビット プロジェクトには使用できません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 使用例  
 次のコードは、**\/Gh** を使ってコンパイルしたときに、`_penter` がどのようにして 2 回呼び出されるかを示しています。つまり、`main` 関数に入ったときと、`x` 関数に入ったときに 1 回ずつ呼び出されます。  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
  **In a function\!**  
**In a function\!**   
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)