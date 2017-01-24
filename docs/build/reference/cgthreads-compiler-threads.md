---
title: "/CGTHREADS (コンパイラ スレッド) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CGTHREADS リンカー オプション"
  - "CGTHREADS リンカー オプション"
  - "-CGTHREADS リンカー オプション"
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CGTHREADS (コンパイラ スレッド)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンク時のコード生成を指定した場合に最適化とコード生成に使う cl.exe スレッドの数を設定します。  
  
## 構文  
  
```  
/CGTHREADS:[1-8]  
```  
  
## 引数  
 number  
 cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。  
  
## 解説  
 **\/CGTHREADS** オプションは、リンク時のコード生成 \([\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\) が指定された場合に、コンパイルの最適化およびコード生成のフェーズで cl.exe が並列で使用するスレッドの最大数を指定します。  既定では、cl.exe は **\/CGTHREADS:4** が指定されているかのように 4 つのスレッドを使用します。  より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。  
  
 ビルドでは複数のレベルの並列化を指定できます。  msbuild.exe スイッチ **\/maxcpucount** は、並列で実行できる MSBuild プロセスの数を指定します。  [\/MP \(複数のプロセスを使用したビルド\)](../../build/reference/mp-build-with-multiple-processes.md) コンパイラ フラグは、ソース ファイルを同時にコンパイルする cl.exe プロセスの数を指定します。  [\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) コンパイラ オプションは、それぞれの cl.exe プロセスが使用するスレッドの数を指定します。  プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。  プロジェクトを並列でビルドする方法の詳細については、「[複数のプロジェクトの並行ビルド](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **［構成プロパティ］**、**［リンカー］** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **［追加オプション］** プロパティに **\/CGTHREADS:**`number` \(`number` は 1 から 8 の値\) が含まれるように変更し、**\[OK\]** をクリックします。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプション](../../build/reference/linker-options.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)