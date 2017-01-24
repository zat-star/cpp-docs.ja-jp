---
title: "/Gm (簡易リビルドの有効化) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.MinimalRebuild"
  - "/Gm"
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.MinimalRebuild"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gm コンパイラ オプション [C++]"
  - "有効化 (簡易リビルドを) コンパイラ オプション [C++]"
  - "Gm コンパイラ オプション [C++]"
  - "-Gm コンパイラ オプション [C++]"
  - "簡易リビルド"
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gm (簡易リビルドの有効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最小リビルドを有効にします。最小リビルドにより、\(ヘッダー \(.h\) ファイルに格納されている\) 変更された C\+\+ クラス定義を含む C\+\+ ソース ファイルを再コンパイルする必要があるかどうかが決定されます。  
  
## 構文  
  
```  
/Gm  
```  
  
## 解説  
 最初のコンパイル時に、コンパイラによってソース ファイルとクラス定義の間の依存関係情報がプロジェクトの .idb ファイルに格納されます。  \(依存関係情報は、どのソース ファイルがどのクラス定義に依存し、どの .h ファイルに定義があるかを示します\)。その後のコンパイルでは、.idb ファイルに格納されている情報が使用され、変更された .h ファイルが含まれている場合でも、ソース ファイルをコンパイルする必要があるかどうかが決定されます。  
  
> [!NOTE]
>  最小リビルドは、クラス定義がインクルード ファイル間で変わらないことに依存します。  .idb ファイル内の依存関係情報はプロジェクト全体に対して作成されるため、クラス定義はプロジェクトに対してグローバルである必要があります \(特定のクラスの定義は 1 つのみである必要があります\)。  プロジェクト内のクラスに複数の定義がある場合は、最小リビルドを無効にします。  
  
 Incremental Linker は [\/ZW \(Windows ランタイムのコンパイル\)](../../build/reference/zw-windows-runtime-compilation.md) オプションの使用により .obj ファイルに含まれる Windows メタデータはサポートされないため、**\/Gm** オプションは **\/ZW** と互換性がありません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コード生成\]** プロパティ ページをクリックします。  
  
4.  **\[最小リビルドを有効にする\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)