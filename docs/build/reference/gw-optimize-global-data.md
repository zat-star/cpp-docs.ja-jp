---
title: "/Gw (グローバル データの最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Gw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gw コンパイラ オプション [C++]"
  - "-Gw コンパイラ オプション [C++]"
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Gw (グローバル データの最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

グローバル データを最適化のために COMDAT セクションにパッケージ化します。  
  
## 構文  
  
```  
/Gw[-]  
```  
  
## 解説  
 **\/Gw** オプションを指定すると、コンパイル時、グローバル データが個々の COMDAT セクションにパッケージ化されます。  既定では、**\/Gw** は無効になっており、明示的に有効にする必要があります。  明示的に無効にするには、**\/Gw\-** を使用します。  **\/Gw** と [\/GL](../../build/reference/gl-whole-program-optimization.md) の両方を有効にすると、リンク時に、プログラム全体の最適化を使用して、複数のオブジェクト ファイル間で COMDAT セクションが比較され、それにより、参照されないグローバル データが除外されたり、同一の読み取り専用のグローバル データがマージされたりします。  その結果、生成されるバイナリ実行可能ファイルのサイズが大幅に小さくなることがあります。  
  
 コンパイルとリンクを別々に実行するときは、[\/OPT:REF](../../build/reference/opt-optimizations.md) リンカー オプションを使用することで、**\/Gw** オプションを指定してコンパイルしたオブジェクト ファイルの参照されないグローバル データを実行可能ファイルから除外できます。  
  
 また、[\/OPT:ICF](../../build/reference/opt-optimizations.md) と [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) のリンカー オプションを一緒に使用することで、**\/Gw** オプションを指定してコンパイルした複数のオブジェクト ファイルの同一の読み取り専用のグローバル データを実行可能ファイルにマージできます。  
  
 詳細については、Visual C\+\+ チーム ブログの「[Introducing \/Gw Compiler Switch \(\/Gw コンパイラ スイッチの概要\)](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\/Gw** が含まれるように **"追加オプション"** プロパティを変更し、**\[OK\]** をクリックします。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)