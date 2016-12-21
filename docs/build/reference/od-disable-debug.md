---
title: "/Od (無効 (デバッグ)) | Microsoft Docs"
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
  - "/od"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Od コンパイラ オプション [C++]"
  - "無効化 (デバッグ) コンパイラ オプション [C++]"
  - "無効化 (最適化を)"
  - "高速コンパイル"
  - "最適化の無効化"
  - "Od コンパイラ オプション [C++]"
  - "-Od コンパイラ オプション [C++]"
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Od (無効 (デバッグ))
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムの最適化処理がすべて無効になり、コンパイル速度が向上します。  
  
## 構文  
  
```  
/Od  
```  
  
## 解説  
 これは、既定のオプションです。  **\/Od** オプションを使用するとコードが移動されないので、デバッグが簡単になります。  デバッグ用コンパイラ オプションの詳細については、「[\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)」を参照してください。  
  
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
 [\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)