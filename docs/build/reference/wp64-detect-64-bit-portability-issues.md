---
title: "/Wp64 (64 ビット移植性の問題の検出) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems"
  - "VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems"
  - "/wp64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Wp64 コンパイラ オプション [C++]"
  - "64 ビット コンパイラ [C++], 検出 (移植性の問題を)"
  - "Wp64 コンパイラ オプション [C++]"
  - "-Wp64 コンパイラ オプション [C++]"
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# /Wp64 (64 ビット移植性の問題の検出)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このコンパイラ オプションは廃止されました。 Visual Studio 2013 より前の Visual Studio のバージョンでは、このオプションは、[\_\_w64](../../cpp/w64.md) キーワードでもマークされている型の 64 ビット移植性の問題を検出します。  
  
## 構文  
  
```  
/Wp64  
```  
  
## 解説  
 既定では、Visual Studio 2013 より前の Visual Studio のバージョンにおいて、**\/Wp64** コンパイラ オプションは Visual C\+\+ の 32 ビットのコンパイラではオフで、Visual C\+\+ の 64 ビットのコンパイラではオンです。  
  
> [!IMPORTANT]
>  [\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) コンパイラ オプションと [\_\_w64](../../cpp/w64.md) キーワードは、Visual Studio 2010 および Visual Studio 2012 で使用されなくなり、Visual Studio 2013 以降ではサポートされません。 このスイッチを使用するプロジェクトを変換すると、変換中にスイッチは移行されません。 このオプションを Visual Studio 2010 または Visual Studio 2012 で使用するには、プロジェクト プロパティの **\[コマンド ライン\]** セクションの **\[追加オプション\]** で、コンパイラ スイッチを入力する必要があります。 コマンド ラインから **\/Wp64** コンパイラ オプションを使用すると、コンパイラはコマンド ラインの警告 D9002 を発行します。 このオプションとキーワードを使用して 64 ビット移植に関する問題を検出する代わりに、64 ビット プラットフォームに対応する Visual C\+\+ コンパイラを使用して、[\/W4](../../build/reference/compiler-option-warning-level.md) オプションを指定します。 詳細については、「[64 ビット用プログラムの構成](../../build/configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。  
  
 次の型の変数は、64 ビット オペレーティング システムで使用されている場合と同様に、32 ビットのオペレーティング システムでテストされます。  
  
-   int  
  
-   long  
  
-   pointer  
  
 通常 64 ビット コンパイラを使用してアプリケーションをコンパイルする場合は、64 ビットのコンパイラがすべての問題を検出するため、32 ビットのコンパイル時には **\/Wp64** を無効にするだけで十分です。 Windows の 64 ビットのオペレーティング システムを対象にする方法の詳細については、「[64 ビット用プログラムの構成](../../build/configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  
  
     詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\/Wp64** を含めるよう \[**詳細オプション**\] ボックスを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [64 ビット用プログラムの構成](../../build/configuring-programs-for-64-bit-visual-cpp.md)