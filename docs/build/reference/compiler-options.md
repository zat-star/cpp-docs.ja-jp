---
title: "コンパイラ オプション | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "cl.exe コンパイラ"
  - "コンパイラ オプション, C++"
  - "IPF Visual C++ コンパイラ"
  - "Itanium Visual C++ コンパイラ"
  - "x64 Visual C++ コンパイラ"
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ オプション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe は、Microsoft C および C\+\+ コンパイラおよびリンカーを制御するツールです。cl.exe は、Microsoft Visual Studio をサポートするオペレーティング システムでのみ実行できます。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。  システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 コンパイラは、COFF \(Common Object File Format\) 形式のオブジェクト \(.obj\) ファイルを生成します。  リンカーは、実行可能 \(.exe\) ファイルまたはダイナミック リンク ライブラリ \(DLL: Dynamic\-Link Library\) を生成します。  
  
 すべてのコンパイラ オプションで、大文字小文字を区別します。  
  
 リンクせずにコンパイルするには、[\/c](../../build/reference/c-compile-without-linking.md) を使用します。  
  
## オプションの検索  
 特定のコンパイラ オプションを見つけるには、次のいずれかの一覧を参照してください。  
  
-   [アルファベット順のコンパイラ オプション](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)  
  
## オプションの指定  
 開発環境での設定方法は、コンパイラの各オプションのトピックで説明します。  開発環境以外からオプションを指定する方法の詳細については、下記を参照してください。  
  
-   [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL のコマンド ファイル](../../build/reference/cl-command-files.md)  
  
-   [環境変数 CL](../../build/reference/cl-environment-variables.md)  
  
## 関連ビルド ツール  
 [NMAKE](../../build/nmake-reference.md) を使用すると、出力ファイルを作成します。  
  
 [BSCMAKE](../../build/reference/bscmake-reference.md) を使用すると、クラス参照をサポートします。  
  
 [リンカー オプション](../../build/reference/linker-options.md)は、プログラムのビルドにも影響を与えます。  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [高速コンパイル](../Topic/Fast%20Compilation.md)   
 [リンカーを呼び出す CL](../../build/reference/cl-invokes-the-linker.md)