---
title: "/Oy (フレーム ポインターの省略) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.OmitFramePointers"
  - "/oy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Oy コンパイラ オプション [C++]"
  - "フレーム ポインターの省略コンパイラ オプション [C++]"
  - "省略 (フレーム ポインターを)"
  - "Oy コンパイラ オプション [C++]"
  - "-Oy コンパイラ オプション [C++]"
  - "スタック フレーム ポインターのコンパイラ オプション [C++]"
  - "抑制 (フレーム ポインターの作成を)"
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Oy (フレーム ポインターの省略)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

呼び出し履歴にフレーム ポインターが作成されなくなります。  
  
## 構文  
  
```  
/Oy[-]  
```  
  
## 解説  
 このオプションを使用すると、フレーム ポインターを設定したり削除したりする必要がなくなるため、関数呼び出しが高速化されます。  また、レジスタ \(Intel 386 以降では EBP\) をもう 1 つ解放して、頻繁に使用される変数と部分式を格納します。  
  
 **\/Oy** ではフレーム ポインターの省略が有効になり、**\/Oy\-** では省略が無効になります。 **\/Oy** は、x86 コンパイラでのみ使用できます。  
  
 コードに EBP ベースのアドレス指定が必要な場合は、**\/Oy–** オプションの後ろに  **\/Ox** オプションを指定するか、[optimize](../../preprocessor/optimize.md) に "**y**" 引数と **off** 引数を指定すると、EBP ベースのアドレス指定が最大限に最適化されます。  コンパイラは、EBP ベースのアドレス指定が必要な場所を検出します。たとえば、`_alloca` 関数および `setjmp` 関数や構造化例外処理が使われている場合にアドレス指定が必要です。  
  
 [\/Ox \(最大限の最適化\)](../../build/reference/ox-full-optimization.md) オプションと [\/O1、\/O2 \(プログラム サイズ、実行速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) オプションを使用すると、**\/Oy** が暗黙的に指定されます。  **\/Ox**、**\/O1**、または **\/O2** の各オプションの後に、**\/Oy–** を指定すると、**\/Oy** が、明示的に使用されていても暗黙に使用されていても無効になります。  
  
 **\/Oy** コンパイラ オプションを使用すると、コンパイラでフレーム ポインター情報が表示されないため、デバッガーの使用が難しくなります。  デバッグ コンパイラ オプション \([\/Z7、\/Zi、\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)\) を指定した場合は、他の最適化コンパイラ オプションの後に **\/Oy\-** オプションを指定することをお勧めします。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[最適化\]** プロパティ ページをクリックします。  
  
4.  **\[フレーム ポインターなし\]** プロパティを変更します。  このプロパティは、**\/Oy** オプションのみ追加または削除します。  **\/Oy\-** オプションを追加する場合は、**\[コマンド ライン\]** をクリックし、**\[追加のオプション\]** を変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A> を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)