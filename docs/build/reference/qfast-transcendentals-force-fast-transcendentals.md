---
title: "/Qfast_transcendentals (超越関数高速化の強制) | Microsoft Docs"
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
  - "/Qfast_transcendentals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qfast_transcendentals"
  - "超越関数高速化の強制"
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qfast_transcendentals (超越関数高速化の強制)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

超越関数のインライン コードを生成します。  
  
## 構文  
  
```  
/Qfast_transcendentals  
```  
  
## 解説  
 このコンパイラ オプションは、超越関数を強制的にインライン コードに変換して、実行速度を向上させます。  このオプションは、**\/fp:except** または **\/fp:precise** とともに使用した場合にのみ有効です。  超越関数に対するインライン コードの生成は、既に **\/fp:fast** での既定の動作になっています。  
  
 このオプションは、**\/fp:strict** との互換性がありません。  浮動小数点コンパイラ オプションの詳細については、「[\/fp \(浮動小数点の動作の指定\)](../../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/Q オプション \(低水準の操作\)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)