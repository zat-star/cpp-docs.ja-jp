---
title: "/cgthreads (コード生成スレッド) | Microsoft Docs"
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
  - "/cgthreads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/cgthreads コンパイラ オプション (C++)"
  - "cgthreads"
  - "cgthreads コンパイラ オプション (C++)"
  - "-cgthreads コンパイラ オプション (C++)"
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /cgthreads (コード生成スレッド)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最適化とコード生成に使用するための cl.exe スレッドの数を設定します。  
  
## 構文  
  
```  
/cgthreads[1-8]  
```  
  
## 引数  
 number  
 cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。  
  
## 解説  
 **\/cgthreads** オプションは、コンパイルの最適化およびコード生成のフェーズで cl.exe が並列で使用するスレッドの最大数を指定します。  **\/cgthreads** と `number` 引数の間にスペースを入れることはできません。  既定では、cl.exe は **\/cgthreads4** が指定されているかのように 4 つのスレッドを使用します。  より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。  このオプションは [\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md) と組み合わせると特に効果的です。  
  
 ビルドでは複数のレベルの並列化を指定できます。  msbuild.exe スイッチ **\/maxcpucount** は、並列で実行できる MSBuild プロセスの数を指定します。  [\/MP \(複数のプロセスを使用したビルド\)](../../build/reference/mp-build-with-multiple-processes.md) コンパイラ フラグは、ソース ファイルを同時にコンパイルする cl.exe プロセスの数を指定します。  **\/cgthreads** オプションは、それぞれの cl.exe プロセスが使用するスレッドの数を指定します。  プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。  プロジェクトを並列でビルドする方法の詳細については、「[複数のプロジェクトの並行ビルド](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[構成プロパティ\]**、**\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **［追加オプション］** プロパティに **\/cgthreads**`N` \(`N` は 1 から 8 の値\) が含まれるように変更し、**\[OK\]** をクリックします。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)