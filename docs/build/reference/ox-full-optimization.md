---
title: "/Ox (最大限の最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ToolOptimization"
  - "/ox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ox コンパイラ オプション [C++]"
  - "高速コード"
  - "最大限の最適化"
  - "Ox コンパイラ オプション [C++]"
  - "-Ox コンパイラ オプション [C++]"
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ox (最大限の最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Ox** コンパイラ オプションを指定すると、サイズを小さくすることよりも実行速度の最適化を優先するコードが生成されます。  
  
## 構文  
  
```  
/Ox  
```  
  
## 解説  
 **\/Ox** コンパイラ オプションを指定することは、次のオプションをすべて使用するのと同じです。  
  
-   [\/Ob \(関数のインライン展開\)](../../build/reference/ob-inline-function-expansion.md) \(オプションのパラメーターは 2 \(**\/Ob2**\)\)  
  
-   [\/Og \(グローバルの最適化\)](../../build/reference/og-global-optimizations.md)  
  
-   [\/Oi \(組み込み関数の生成\)](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)  
  
-   [\/Ot \(高速なコードを優先\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)  
  
-   [\/Oy \(フレーム ポインターの省略\)](../../build/reference/oy-frame-pointer-omission.md)  
  
 **\/Ox** は、次のオプションと併用できません。  
  
-   [\/O1 \(最小サイズ\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/O2 \(最高速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/Od \(無効 \(デバッグ\)\)](../../build/reference/od-disable-debug.md)  
  
 **\/Ox** コンパイラ オプションを指定すると、名前付き戻り値の最適化も有効になります。この最適化では、スタック ベースの戻り値のコンストラクターとデストラクターがコピーされません。  詳細については、「[\/O1、\/O2 \(プログラム サイズ、実行速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)」を参照してください。  
  
 **\/Ox** コンパイラ オプションと [\/Os \(小さなコードを優先\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) を結合した **\/Oxs** コンパイラ オプションを指定すると、**\/Ox** コンパイラ オプションを取り消すことができます。  この結合オプションでは、コード サイズを小さくすることが優先されます。  
  
 通常は、**\/Ox** の代わりに [\/O2 \(最高速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) を、**\/Oxs** の代わりに [\/O1 \(最小サイズ\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) を指定します。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[最適化\]** プロパティ ページをクリックします。  
  
4.  **\[最適化\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>」を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)