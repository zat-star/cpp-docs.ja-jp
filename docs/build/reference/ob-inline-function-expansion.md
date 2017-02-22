---
title: "/Ob (関数のインライン展開) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion"
  - "VC.Project.VCCLCompilerTool.InlineFunctionExpansion"
  - "/ob"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ob コンパイラ オプション [C++]"
  - "/Ob0 コンパイラ オプション [C++]"
  - "/Ob1 コンパイラ オプション [C++]"
  - "/Ob2 コンパイラ オプション [C++]"
  - "適用可能なコンパイラ オプション [C++]"
  - "無効化コンパイラ オプション [C++]"
  - "インライン展開, コンパイラ オプション"
  - "インライン関数, 関数の展開コンパイラ オプション [C++]"
  - "Ob コンパイラ オプション [C++]"
  - "-Ob コンパイラ オプション [C++]"
  - "Ob0 コンパイラ オプション [C++]"
  - "-Ob0 コンパイラ オプション [C++]"
  - "Ob1 コンパイラ オプション [C++]"
  - "-Ob1 コンパイラ オプション [C++]"
  - "Ob2 コンパイラ オプション [C++]"
  - "-Ob2 コンパイラ オプション [C++]"
  - "only __inline コンパイラ オプション [C++]"
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ob (関数のインライン展開)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数のインライン展開を制御します。  
  
## 構文  
  
```  
/Ob{0|1|2}  
```  
  
## 引数  
 **0**  
 インライン展開を無効にします。  既定では、展開はすべての関数でコンパイラの裁量で行われ、一般に「*自動インライン展開*」と呼ばれます。  
  
 **1**  
 [inline](../../misc/inline-inline-forceinline.md)、[\_\_inline](../../misc/inline-inline-forceinline.md)、または [\_\_forceinline](../../misc/inline-inline-forceinline.md) としてマークされた関数の展開のみ、またはクラス宣言で定義された C\+\+ メンバー関数にある展開のみが許可されます。  
  
 **2**  
 既定値。  `inline`、`__inline`、または `__forceinline` としてマークされた関数の展開、およびコンパイラが選択するその他すべての関数が許可されます。  
  
 **\/Ob2** は、[\/O1、\/O2 \(プログラム サイズ、実行速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、または [\/Ox \(最大限の最適化\)](../../build/reference/ox-full-optimization.md) を使用する場合のみ有効になります。  
  
 このオプションでは、**\/O1**、**\/O2**、**\/Ox**、または **\/Og** を使用して最適化を有効にする必要があります。  
  
## 解説  
 インライン展開に関するオプションとキーワードは、インライン展開の対象となる候補をコンパイラに示すだけです。  すべての関数がインライン展開になるという保証はありません。  インライン展開は無効にすることができますが、`__forceinline` キーワードを使用しても、特定の関数のインライン展開をコンパイラに強制することはできません。  
  
 `#pragma` [auto\_inline](../../preprocessor/auto-inline.md) ディレクティブを使用して、関数をインライン展開の候補対象から除外することができます。  `#pragma` [intrinsic](../../preprocessor/intrinsic.md) ディレクティブも参照してください。  
  
> [!NOTE]
>  プロファイリングのテスト実行から収集される情報により、**\/Ob**、**\/Os**、または **\/Ot** を指定する場合に有効な最適化がオーバーライドされます。  詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **［構成プロパティ］**、**［C\/C\+\+］** の順に展開して、**［最適化］** をクリックします。  
  
3.  **関数のインライン展開** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>」を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)