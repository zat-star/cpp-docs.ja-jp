---
title: "/D (プリプロセッサの定義) | Microsoft Docs"
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
  - "VC.Project.VCNMakeTool.PreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.PreprocessorDefinitions"
  - "/d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/D コンパイラ オプション [C++]"
  - "定数, 定義"
  - "D コンパイラ オプション [C++]"
  - "-D コンパイラ オプション [C++]"
  - "マクロ, コンパイル"
  - "プリプロセッサ定義シンボル"
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /D (プリプロセッサの定義)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ソース ファイルのプリプロセッサ シンボルを定義します。  
  
## 構文  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## 解説  
 このシンボルを `#if` または `#ifdef` と一緒に使用すると、ソース コードを条件付きでコンパイルできます。  シンボル定義は、コードで再定義されるまで、または `#undef` ディレクティブによってコードで未定義になるまで有効です。  
  
 **\/D** は、ソース コード ファイルの先頭にある `#define` ディレクティブと同じ効果があります。ただし、**\/D** ではコマンド ラインの引用符が削除され、`#define` では保持されます。  
  
 既定では、シンボルに関連付けられる値は 1 です。  たとえば、**\/D**`name` は、**\/D**`name`**\=1** と同じです。  この記事の最後の例では、`1` を出力するための **TEST** の定義が示されています。  
  
 **\/D** `name` **\=** を使用してコンパイルすると、シンボルには値が関連付けられません。  シンボルは引き続きコードの条件コンパイルに使用できますが、何も指定されていないものとして評価されます。  この例では、**\/DTEST\=** を使用してコンパイルすると、エラーが発生します。  この動作は、値を指定して、または値を指定せずに `#define` を使用する場合と似ています。  
  
 次のコマンドを実行すると、TEST.c で DEBUG シンボルが定義されます。  
  
 **CL \/DDEBUG  TEST.C**  
  
 次のコマンドを実行すると、TEST.c からすべての `__far` キーワードが削除されます。  
  
 **CL \/D\_\_far\=  TEST.C**  
  
 **CL** 環境変数には、等号 \(\=\) を含む文字列を設定できません。  **CL** 環境変数で **\/D** を使用するには、等号 \(\=\) ではなくシャープ記号 \(\#\) を指定する必要があります。  
  
```  
SET CL=/DTEST#0  
```  
  
 コマンド プロンプトでプリプロセッサ シンボルを定義する場合は、コンパイラ解析規則とシェル解析規則の両方を考慮してください。  たとえば、プログラムでパーセント記号のプリプロセッサ シンボル \(%\) を定義するには、コマンド プロンプトでパーセント記号 2 文字 \(%%\) を指定します。パーセント記号を 1 文字だけ指定すると、解析エラーが発生します。  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  左ペインで、**\[構成プロパティ\]**、**\[C\/C\+\+\]**、**\[プリプロセッサ\]** の順に選択します。  
  
3.  右ペインの **\[プリプロセッサの定義\]** プロパティの右側の列で、ドロップダウン メニューを開き、**\[編集\]** を選択します。  
  
4.  **\[プリプロセッサの定義\]** ダイアログ ボックスで、1 つ以上の定義を追加 \(1 行に 1 つ\)、変更、または削除します。  **\[OK\]** をクリックして変更を保存します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>」を参照してください。  
  
## 使用例  
  
```  
// cpp_D_compiler_option.cpp  
// compile with: /DTEST  
#include <stdio.h>  
  
int main( )  
{  
    #ifdef TEST  
        printf_s("TEST defined %d\n", TEST);  
    #else  
        printf_s("TEST not defined\n");  
    #endif  
}  
```  
  
  **TEST defined 1**   
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [\/U、\/u \(定義済みマクロ シンボルの未定義化\)](../Topic/-U,%20-u%20\(Undefine%20Symbols\).md)   
 [\#undef ディレクティブ](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [\#define ディレクティブ](../../preprocessor/hash-define-directive-c-cpp.md)