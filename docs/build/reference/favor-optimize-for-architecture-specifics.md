---
title: "/favor (アーキテクチャ固有の最適化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/favor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-favor コンパイラ オプション [C++]"
  - "/favor コンパイラ オプション [C++]"
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# /favor (アーキテクチャ固有の最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/favor:** `option` は 特定のアーキテクチャまたは AMD と Intel アーキテクチャのマイクロアーキテクチャの仕様に合わせて最適化されるコードを作成します。  
  
## 構文  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## 解説  
 **\/favor:blend**  
 \(x86 および x64\) および AMD Intel アーキテクチャのマイクロアーキテクチャの仕様に合わせて最適化されるコードを作成します。  **\/favor:blend** が特定のプロセッサで最大限のパフォーマンスを得ることができない場合もありますが、x86 および x64 プロセッサで最適なパフォーマンスが得られるようにデザインされています。  既定で、**\/favor:blend** が有効になります。  
  
 **\/favor:ATOM**  
 \(x86 および x64\) は、Intel プロセッサと Intel プロセッサは Centrino テクノロジの仕様に合わせて最適化されるコードを作成します。  コードは、**\/favor:ATOM** を使用して、または Intel プロセッサの Intel SSSE3、SSE3、SSE2 と SSE 命令が生成される可能性のある生成されます。  
  
 **\/favor:AMD64**  
 \(x64\) のみ AMD Opteron 用に生成されたコードを、64 ビット拡張機能をサポートする Athlon プロセッサを最適化します。  最適化されたコードは、すべての x64 互換のプラットフォームで動作します。  コードは、**\/favor:AMD64** を使用して Intel64 をサポートする Intel プロセッサで実行すると、パフォーマンスが低下する可能性が生成されます。  
  
 **\/favor:INTEL64**  
 \(x64\) のみ Intel64 をサポートする Intel プロセッサ用に生成されたコードを最適化するので、通常、このプラットフォームでより高いパフォーマンスが得られます。  結果コードはどの x64 プラットフォームで動作します。  コードは、**\/favor:INTEL64** と AMD Opteron で実行すると、パフォーマンス、64 ビット拡張機能をサポートする Athlon プロセッサが生じる可能性が生成されます。  
  
> [!NOTE]
>  Intel64 アーキテクチャは、以前は Extended Memory 64 Technology と呼ばれ、対応するコンパイラ オプションは **\/favor:EM64T** でした。  
  
 [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] アーキテクチャ用にプログラミングする方法の詳細については、「[x64 ソフトウェア規約](../../build/x64-software-conventions.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)